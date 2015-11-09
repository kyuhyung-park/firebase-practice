# Firebase Practice

## install
```
<script src="https://cdn.firebase.com/js/client/2.3.1/firebase.js"></script>
```

## Connection
```
var ref = new Firebase("https://test--firebase.firebaseio.com/web/saving-data/fireblog");
var usersRef = ref.child("users");
```

## Write Data
```
usersRef.set({
  alanisawesome: {
    date_of_birth: "June 23, 1912",
    full_name: "Alan Turing"
  },
  gracehop: {
    date_of_birth: "December 9, 1906",
    full_name: "Grace Hopper"
  }
});
```

## Read Data
```
usersRef.on("value", function(snapshot) {
  console.log(snapshot.val());
}, function (errorObject) {
  console.log("The read failed: " + errorObject.code);
});
```
```
ref.child("users/gracehop/date_of_birth").on("value", function(snapshot) {
  console.log(snapshot.val()); // "December 9, 1906"
}, function (errorObject) {
  console.log("The read failed: " + errorObject.code);
});
```
