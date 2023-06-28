<template>
  <div id="webglScene" />
</template>

<script>
import * as THREE from 'three'
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
import { DRACOLoader } from 'three/examples/jsm/loaders/DRACOLoader.js'
export default {
  name: 'Scene',
  props: {
    loaded: Boolean,
  },
  data() {
    return {
      scrollPosY: 0,
      sizes: {
        width: '',
        height: '',
      },
      controls: null,
      textureLoader: null,
      mesh: null,
      cursor: {
        x: 0,
        y: 0,
      },
      camera: null,
      scene: null,
      renderer: null,
      labelRenderer: null,
      bull: null,
      spriteOne: null,
      spriteTwo: null,
      spriteThree: null,
      spriteText: null,
      windowHalfX: null,
      windowHalfY: null,
      targetX: 0,
      targetY: 0,
      gltfLoader: null,
      text: null,
      loaderManager: null,
      sizesAbstract: null,
      gui: null,
      lightGroup: null,
    }
  },
  watch: {
    loaded(val) {
      if (val) {
        new ResizeObserver(this.resize).observe(
          document.querySelector('#__nuxt')
        )
      }
    },
  },
  beforeMount() {
    window.addEventListener('scroll', this.updateScrollPos)
  },

  mounted() {
    this.renderer = new THREE.WebGLRenderer({
      alpha: true,
      powerPreference: 'high-performance',
      antialias: true,
      stencil: false,
      depth: true,
    })
    this.$el.appendChild(this.renderer.domElement)
    this.init()
    this.$events.on('frame:frame', this.animate)
  },

  methods: {
    init() {
      const axesHelper = new THREE.AxesHelper(600)
      this.scene = new THREE.Scene()
      // sizes
      this.sizes.width = window.innerWidth
      this.sizes.height = window.innerHeight
      this.windowHalfX = this.sizes.width / 2
      this.windowHalfY = this.sizes.height / 2
      // main

      /**
       * Loaders
       */
      this.loaderManager = new THREE.LoadingManager()
      const dracoLoader = new DRACOLoader()
      dracoLoader.setDecoderPath('/barcelona-event/draco/')

      this.gltfLoader = new GLTFLoader(this.loaderManager)
      this.gltfLoader.setDRACOLoader(dracoLoader)

      this.textureLoader = new THREE.TextureLoader()

      /**
       * Camera
       */
      this.camera = new THREE.PerspectiveCamera(
        70,
        this.sizes.width / this.sizes.height,
        10,
        2000
      )
      this.camera.position.z = 1200
      this.camera.aspect = this.sizes.width / this.sizes.height
      this.normalizeCamera()
      this.camera.updateProjectionMatrix()

      // Controls
      this.controls = new OrbitControls(this.camera, this.renderer.domElement)
      window.addEventListener('mousemove', this.mouseMove)

      this.renderer.shadowMap.autoUpdate = false
      this.renderer.shadowMap.needsUpdate = true
      this.renderer.shadowMap.enabled = true
      this.renderer.info.autoReset = false
      this.renderer.physicallyCorrectLights = true
      this.renderer.setSize(this.sizes.width, this.sizes.height)
      this.renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))

      this.scene.add(this.camera)
      this.light()
      this.models()
    },

    light() {
      // Directional light
      const directionalLight = new THREE.DirectionalLight(0xffffff, 0.5)
      directionalLight.position.set(100, 100, 100)
      // Point light
      const pointLight = new THREE.PointLight(0xffffff, 600, 0, 1)
      pointLight.position.set(-50, 150, 300)
      // Helpers
      const sphereSize = 100
      const pointLightHelper = new THREE.PointLightHelper(
        pointLight,
        sphereSize
      )
      this.lightGroup = new THREE.Group()
      this.lightGroup.add(directionalLight)
      this.lightGroup.add(pointLight)
      this.scene.add(this.lightGroup)
    },
    models() {
      this.gltfLoader.load('/barcelona-event/bull_web2.glb', (gltf) => {
        this.bull = gltf.scene
        if (this.sizes.width <= 576) {
          this.bull.rotation.y = -0.5
        }
        this.scene.add(this.bull)
        this.bull2 = gltf.scene.clone()
        this.scene.add(this.bull2)
      })
    },
    updateObjectParams(obj, elSelector) {
      const element = document.querySelector(elSelector)
      if (!element) return
      const sizes = element.getBoundingClientRect()
      const scale = sizes.width * 0.8
      if (obj !== undefined) {
        obj.scale.set(scale, scale, scale)
        obj.position.y = window.innerHeight / 2 - sizes.height / 2 - sizes.top - window.scrollY
        obj.position.x = sizes.left - this.$el.clientWidth / 2 + sizes.width / 2
      }
    },
    mouseMove(e) {
      this.cursor.x = e.clientX - this.windowHalfX
      this.cursor.y = e.clientY - this.windowHalfY
    },
    animate() {
      this.resize()
      /* change camera position with scroll (down) */
      // this.scrollPosY = -this.scrollPosY * 0.001

      this.targetX = this.cursor.x * 0.001
      this.targetY = this.cursor.y * 0.001
      if (this.bull !== null) {
        if (this.sizes.width <= 576) {
          this.bull.rotation.y = -0.5
          this.bull.rotation.x +=
            0.1 * (this.targetY - this.bull.rotation.x / 2)
        } else if (this.sizes.width <= 992) {
          this.bull.rotation.x +=
            0.1 * (this.targetY - this.bull.rotation.x / 2)
          this.bull2.rotation.x += 0.1 * (this.targetY - this.bull2.rotation.x)
          this.bull.rotation.y += 0.1 * (this.targetX - this.bull.rotation.y)
          this.bull2.rotation.y +=
            0.1 * (this.targetX - this.bull2.rotation.y * 2)
        } else {
          this.bull.rotation.x +=
            0.1 * (this.targetY - this.bull.rotation.x / 2)
          this.bull2.rotation.x += 0.1 * (this.targetY - this.bull2.rotation.x)
          this.bull.rotation.y += 0.1 * (this.targetX - this.bull.rotation.y)
          this.bull2.rotation.y +=
            0.1 * (this.targetX - this.bull2.rotation.y * 2)
          this.camera.position.y = -this.scrollPosY
          if (this.lightGroup !== null) {
            this.lightGroup.position.y = -this.scrollPosY
            this.lightGroup.position.x = -this.scrollPosY / 50
          }
        }
      }
      this.renderer.render(this.scene, this.camera)
    },
    normalizeCamera() {
      this.camera.fov =
        2 *
        Math.atan(this.sizes.height / 2 / this.camera.position.z) *
        (180 / Math.PI)
    },
    resize() {
      this.normalizeCamera()
      // Update sizes
      this.sizes.width = window.innerWidth
      this.sizes.height = window.innerHeight
      // Update camera
      this.camera.aspect = this.sizes.width / this.sizes.height
      this.camera.updateProjectionMatrix()
      this.renderer.setSize(this.sizes.width, this.sizes.height)
      this.renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))
      if (this.bull2 !== null) {
        this.updateObjectParams(this.bull2, '.moneyback-bull-holder-img')
      }
      if (this.bull !== null) {
        this.updateObjectParams(this.bull, '.banner-bull-holder-img')
      }
    },
    removeScene(object) {
      const selectedObject = this.scene.getObjectByName(object.name)
      this.scene.remove(selectedObject)
    },
    updateScrollPos(e) {
      this.scrollPosY = window.scrollY
    },
  },
  beforeDestroy() {
    this.$events.off('frame:frame', this.animate)
    window.removeEventListener('scroll', this.updateScrollPos)
    window.removeEventListener('mousemove', this.mouseMove)
    this.scene.remove(this.bull2)
    this.scene.remove(this.bull)
    this.scene.remove(this.lightGroup)
    this.scene.remove(this.camera)
  },
}
</script>

<style lang="scss" scoped>
#webglScene {
  height: 100vh;
  width: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
  position: absolute;
  z-index: 3;
  @media (min-width: 992px) {
    position: fixed;
  }
  canvas {
    margin: 0;
    height: 100%;
    width: 100%;
    display: block;
  }
}
</style>
