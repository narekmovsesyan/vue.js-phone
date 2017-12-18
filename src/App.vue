<template>
  <div id="app">
    <h1 style="text-align: center">{{ msg }}</h1>

  <div class="container">
    <div class="row no-gutters">
      <div class="col-6 col-md-4">
        <div class="background-style" v-bind:style="backColor">
          <p v-bind:class="[classStyle, fontFamilyClass, fontSizeClass, fontWeightClass]" class="text-p-style">{{text}}</p>
            <div style="text-align: center" v-bind:class="phoneColorClass">
               <div class="phone-menu-parent" v-bind:style="phoneMenuColor">
                   <div class="phone-menu-child">&#10006;
                      Camera Roll
                       <span class="phone-menu-next">
                           NEXT
                       </span>
                   </div>
               </div>

            <div class="phone-down-menu" v-bind:style="phoneMenuColor">
                   <div class="phone-down-menu-left-icon"><</div>
                   <div class="phone-down-menu-right-icon">></div>
               </div>
            </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-md-8">
        <div class="right-big-div">
         <div class="float-left title-style">
          Screenshot
         </div>

         <div class="col-md-6 input-group div-distance">
           <span class="input-group-addon" id="basic-addon1"><img src="./assets/upload.png"></span>
           <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
         </div>
         <br>

          <div class="float-left second-title">
            Caption
          </div>

          <div class="form-group div-distance">
            <input type="email" class="form-control" v-on:input = "text=$event.target.value " aria-describedby="emailHelp" placeholder="Enter text">
          </div>

          <div class="float-left title-style">
            Layout
          </div>

          <div class="div-distance">
            <div class="col-md-6">
                <select size="1" v-model="textStyle" v-on:change="chengeStyle"  class="form-control">
                    <option value="" selected disabled hidden>Choose here</option>
                    <option value="bold" data-multiplier = "bold">bold</option>
                    <option value="underline" data-multiplier = "underline">underline</option>
                    <option value="line-through" data-multiplier = "line-through">line through</option>
                    <option value="italic" data-multiplier = "italic">italic</option>
                </select>
            </div>

            <div class="col-md-6">
                <select size="1" v-model="phoneColorModel" v-on:change="phoneColor"  class="form-control">
                    <option value="" selected disabled hidden>Choosen white</option>
                    <option value="phone-image-black">black</option>
                    <option value="phone-image-white">white</option>
                </select>

            </div>
          </div>

          <div class="float-left title-style">
            Layout
          </div>

          <div class="div-distance">
            <div class="col-md-4">
                  <select size="1" v-model="fontFamilyModel" v-on:change="fontFamily" class="form-control">
                      <option value="" selected disabled>Choosen font family</option>
                      <option value="font-style-fantasy">Fantasy</option>
                      <option value="font-style-cursive">Cursive</option>
                      <option value="font-style-monospace">Monospace</option>
                  </select>
            </div>

            <div class="col-md-2">
              <select v-model="fontSizeModel" v-on:change="fontSize" id="inputState4" class="form-control">
                <option value="" selected disabled>size</option>
                <option value="font-size-13">13</option>
                <option value="font-size-14">14</option>
                <option value="font-size-15">15</option>
                <option value="font-size-17">17</option>
                <option value="font-size-19">19</option>
              </select>
            </div>

            <div class="col-md-2">
              <select v-model="fontWeightModel" v-on:change="fontWeightFun" id="inputState5" class="form-control">
                <option value="" selected disabled>weight</option>
                <option value="font-weight-400">400</option>
                <option value="font-weight-900">900</option>
                <option value="font-weight-bolder">bolder</option>
              </select>
            </div>

            <div class="col-md-4 color-style" v-on:input="phoneMenuColor.backgroundColor=$event.target.value">
              Color <input value="#2c3e50" type="color" class="color-position">
            </div>
          </div>

          <div class="float-left title-style">
            Background
          </div>

          <div class="col-md-4 color-style" v-on:input="backColor.backgroundColor=$event.target.value" style="margin-top: 8px;">
           Color <input value="#A8DBD7" type="color" class="color-position">
          </div>
        </div>
      </div>
    </div>
  </div>

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Appsrore Preview Image Builder',
      text: 'Text Appsrore Appsrore Appsrore Appsrore',
      classStyle:'',
      textStyle: '',
      phoneColorClass: 'phone-image-white',
      phoneColorModel: '',
      fontFamilyClass: '',
      fontFamilyModel: '',
      fontSizeClass: 'font-size-17',
      fontSizeModel: '',
      fontWeightClass:'',
      fontWeightModel:'',
      backgroundColorClass:'',
      backgroundColorModel:'',
      backColor:{
          backgroundColor: '#A8DBD7'
      },
      phoneMenuColor:{
          backgroundColor: '#29282D'
      },
    }
  },

  methods: {
      chengeStyle: function() {
          this.classStyle = this.textStyle;
      },
      phoneColor: function(){
          this.phoneColorClass = this.phoneColorModel;
      },
      fontFamily: function(){
          this.fontFamilyClass = this.fontFamilyModel;
      },
      fontSize: function(){
          this.fontSizeClass = this.fontSizeModel;
      },
      fontWeightFun: function(){
          this.fontWeightClass = this.fontWeightModel;
      },
  }
}

</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

  .color-style{
    border: 1px solid rgb(201, 201, 201);
    height: 34px;
    border-radius: 3px;
  }
  .color-position{
    margin-top: 4px;
  }

</style>
