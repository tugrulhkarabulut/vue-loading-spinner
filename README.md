# vue-loading-spinner
Customizable loading animation for your Vue App

# Basic Usage

Suppose you named this component v-spinner

 Basic spinner with no text
v-spinner :weight="0.2" :size="5"></v-spinner>

 Spinner with text and custom timing
v-spinner :weight="0.2" :size="5" :noText="false" :timing="'ease-in'">
    <span>Waiting for response...</span>
</v-spinner>

# Properties
weight: 
  Thickness of the circle
  default: 0.5
size: 
  Size of the circle
  default value: 5 
color:
  default value: Black
timing: 
  Animation timing function
  default value: cubic-bezier(0.47, 0.32, 0.71, 0.37)
noText: 
  default value: true

