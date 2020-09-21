<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>
<body>

<div ng-app="myApp" ng-controller="arrCtrl"> 
<p>First Name: <input type="text" ng-model="fname"></p>
<p>Last Name: <input type="text" ng-model="lname"></p>
<p>Note: <input type="text" ng-model="note"></p>
<p>Birth Date: <input type="text" ng-model="date"></p>
<p ng-bind="fname"></p>
<ul>
<li ng-repeat="x in students | filter :{'fname' : fname , 'lname' : lname , 'note' : note, 'date': date}">{{x.fname + ", " + x.lname + "," + x.note + " , " + x.date}}</li>
</ul>

</div>

<script>
var app = angular.module('myApp', []);
app.controller('arrCtrl', function($scope) {
    $scope.students = [
        {"fname" : "Daria", "lname" : "Cramar" , "note" : "8.5" , "date" : "07.02.1998"},
        {"fname" : "Alisa", "lname" : "Gol" , "note" : "9.5" , "date" : "07.02.1996"},
         {"fname" : "Oleg", "lname" : "Bort" , "note" : "7.5" , "date" : "07.03.1998"},
          {"fname" : "Maxim", "lname" : "Morar" , "note" : "8.6" , "date" : "07.02.1997"},
    ];
});
</script>

</body>
</html>
