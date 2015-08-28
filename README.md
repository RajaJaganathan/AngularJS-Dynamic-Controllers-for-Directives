## AngularJS-Dynamic-Controllers-for-Directives

In directive you just add two new property called controller and name property are exactly needed here.

Important things to note in directive

```
scope:{}, //isolate scope
controller : "@", // @ symbol
name:"controllerName", // controller names property points to controller.
```
###HTML Markup:

```
<communicator controller-name="PhoneCtrl" ></communicator>
<communicator controller-name="LandlineCtrl" ></communicator>
```

### Angularjs Controller and Directive:

```
var app = angular.module('myApp',[]).
directive('communicator', function(){
return {
    restrict : 'E',
    scope:{},
    controller : "@",
    name:"controllerName", 
    template:"<input type='text' ng-model='message'/><input type='button' value='Send Message' ng-click='sendMsg()'><br/>"          
  }   
}).
controller("PhoneCtrl",function($scope){
 $scope.sendMsg = function(){
     alert( $scope.message + " : sending message via Phone Ctrl");
    }
}).
controller("LandlineCtrl",function($scope){
    $scope.sendMsg = function(){
        alert( $scope.message + " : sending message via Land Line Ctrl ");
    }
});

```

[Live demo](http://jsfiddle.net/p6Hb4/ "AngularJS-Dynamic-Controllers-for-Directives")

