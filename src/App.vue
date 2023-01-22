<template>

    <div class="header">
      <div class="float-left">
        <div class="float-left">
          <img :src="require('../assets/logo.svg')" width="125" height="61">
        </div>
        <div class="float-right border-left" style="height: 61px;">
          <h1 id="header-text">Playground Drawing Tool</h1>
        </div>
      </div>
      <div class="float-right">
        <button id="finalizeBtn">Finalize & Get a Quote</button>
      </div>
    </div>
    <!-- <div class="hystmodal" id="myModal" aria-hidden="true">
      <div class="hystmodal__wrap">
        <div class="loading__window modal_window" role="dialog" aria-modal="true">
          <div class="loading-text">
            Loading, please wait.
          </div>
          <div>
            <img :src="require('../assets/spinner.svg')" height="100px" width="100px">
          </div>
        </div>
      </div>
    </div>

    <div class="hystmodal" id="finalizeModal" aria-hidden="true">
      <div class="hystmodal__wrap">
        <div class="finalizeModal__window modal_window" role="dialog" aria-modal="true">
          <div class="finalize-modal-text">
            <form>
              <label>
                Name
              </label>
              <br>
              <input type="text" id="name" />
              <br>
              <label>
                Description
              </label>
              <br>
              <input type="text" id="description">
            </form>
            <button id="saveBtn">Save</button>
            <button id="cancelBtn">Cancel</button>
          </div>
        </div>
      </div>
    </div> -->

    <div id="container">
      <div class="drawing">
        <canvas crossOrigin="anonymous" id="c"></canvas>
      </div>
      <div id="toolbar-container">
        <div id="toolbar">
          <div class="tool"
            data-tg-tour='The final step<br> <img src="b6e5ff47724ef4eb6a69.svg" height="500" width="500">'
            data-tg-order="99">
            <div class="tool-item" id="pan">
              <img :src="require('../assets/pan.svg')" width="24" height="24">
              <div>Pan</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="select">
              <img :src="require('../assets/select.svg')" width="24" height="24">
              <div>Select</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="connect">
              <img :src="require('../assets/diagonal-line.svg')" width="24" height="24">
              <div>Surface</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="drawcircle">
              <img :src="require('../assets/circle.svg')" width="24" height="24">
              <div>Circle</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="drawrectangle">
              <img :src="require('../assets/rectangle.svg')" width="24" height="24">
              <div>Square</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="delete">
              <img :src="require('../assets/trash.svg')" width="24" height="24">
              <div>Delete</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="notes">
              <img :src="require('../assets/note.svg')" width="24" height="24">
              <div>Note</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="compass">
              <img :src="require('../assets/compass.svg')" width="24" height="24">
              <div>Compass</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="callout">
              <img :src="require('../assets/callout.svg')" width="24" height="24">
              <div>Callout</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="undo">
              <img :src="require('../assets/undo.svg')" width="24" height="24">
              <div>Undo</div>
            </div>
          </div>
          <div class="tool">
            <div class="tool-item" id="redo">
              <img :src="require('../assets/redo.svg')" width="24" height="24">
              <div>Redo</div>
            </div>
          </div>
        </div>
      </div>

      <div id="right-sidebar">
        <div class="library">
          <div id="right-sidebar-header">PLAYGROUND LIBRARIES</div>
        </div>

        <div class="library" data-dropdown="equipment">
          <div id="right-sidebar-header">Equipment</div>
          <img :src="require('../assets/arrow_drop_down.svg')" width="24" height="24">
        </div>
        <div class="library-items-container hide" id="equipment-items">
          <div class="library-item equipment">
            <img class="float-left" :src="require('../assets/TreeThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Tree</div>
          </div>
          <div class="library-item">
            <img class="float-left" :src="require('../assets/ShrubThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Bush</div>
          </div>
        </div>

        <div class="library" data-dropdown="bench">
          <div id="right-sidebar-header">Benches</div>
          <img :src="require('../assets/arrow_drop_down.svg')" width="24" height="24">
        </div>
        <div class="library-items-container hide" id="bench-items">
          <div class="library-item">
            <img class="float-left" :src="require('../assets/TreeThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Tree</div>
          </div>
          <div class="library-item">
            <img class="float-left" :src="require('../assets/ShrubThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Bush</div>
          </div>
        </div>

        <div class="library" data-dropdown="shade">
          <div id="right-sidebar-header">Shade Screens</div>
          <img :src="require('../assets/arrow_drop_down.svg')" width="24" height="24">
        </div>
        <div class="library-items-container hide" id="shade-items">
          <div class="library-item">
            <img class="float-left" :src="require('../assets/TreeThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Tree</div>
          </div>
          <div class="library-item">
            <img class="float-left" :src="require('../assets/ShrubThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Bush</div>
          </div>
        </div>

        <div class="library" data-dropdown="surface">
          <div id="right-sidebar-header">Surface Hatch</div>
          <img :src="require('../assets/arrow_drop_down.svg')" width="24" height="24">
        </div>
        <div class="library-items-container hide" id="surface-items">
          <div class="library-item" id="polygon">
            <img class="float-left" :src="require('../assets/TreeThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Purple Surface</div>
          </div>
        </div>

        <div class="library" data-dropdown="landscape">
          <div id="right-sidebar-header">Landscape</div>
          <img :src="require('../assets/arrow_drop_down.svg')" width="24" height="24">
        </div>
        <div class="library-items-container" id="landscape-items">
          <div class="library-item" id="tree">
            <img class="float-left" :src="require('../assets/TreeThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Tree</div>
          </div>
          <div class="library-item" id="shrub">
            <img class="float-left" :src="require('../assets/ShrubThumbnail.png')" width="45" height="45">
            <div class="float-right library-item-text">Bush</div>
          </div>
        </div>
      </div>
      <!-- <div data-tg-tour="<span>My first tour</span>"> ... </div> -->

    </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import drawingFunctions from './js/drawingfunctions.js';
import grid from './js/grid.js';
import { fabric } from "fabric";

export default {
  name: 'App',
  data() {
    return {
      // base tool
      canvas: null,
      drawingMode: '',
      lineOrientation: '',

      calloutNumber: 1,

      // temp variable for objects being drawn
      line: new fabric.Line(),
      rectangle: new fabric.Rect(),
      circle: new fabric.Circle(),

      inDrawingMode: '',
      isDrawing: false,

      connectCircles: [],
      connectLines: [],
      
      lineCircle: {
        x: 0,
        y: 0,
        isInCircle: false
      },

      lineCircleSize: 16,
      dontDrawStartCircle: false,
      dontDrawEndCircle: false,

      currentLineTextbox: null
    }
  },

  mounted() {
    this.canvas = new fabric.Canvas('c', {
      selection: true,
      preserveObjectStacking: true
    });

    // this.drawingMode = drawingMode;
    // this.lineOrientations = lineOrientations;

    fabric.Object.prototype.transparentCorners = false;

    drawingFunctions.foo();

    this.canvas.isDrawingMode = true;
    this.canvas.freeDrawingBrush.width = 5;

    grid.setGrid(this.canvas, require('../public/grid.png'));
    //this.canvas.setBackgroundImage(require('../assets/grid.png'), () => {}, { objectCaching: false });

    this.resizeCanvas(); 
  },

  created() {
    // selection should allow a user to drag over objects to select them

    //this.canvas.initState();
  },

  methods: {
    resizeCanvas() {

        const container = document.getElementsByClassName('drawing')[0];
        const canvasContainer = container.getElementsByClassName('canvas-container')[0];
        canvasContainer.style.width = 'unset';
        canvasContainer.style.height = 'unset';
        this.canvas.setDimensions({ width: container.offsetWidth, height: container.offsetHeight });
    }
  }
}
</script>

<style lang="scss" scoped>
@import "app.scss";
</style>