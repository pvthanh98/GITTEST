## Store collection
```javascript
{
  _id: {type: ObjectID, unique:true},
  email: {type:String, unique:true},
  password: { type:String },
  name:  String, 
  description: String,
  address:   String,
  latitude: {type:Number, default:-1},
  longtitude: {type:Number, default:-1},
  image: { type: String, default : "default_store.jpg"},
  city: {type: Schema.Types.ObjectId, ref: "city"},
  rating: {
    five: { type:Number, default: 0 },
    four: { type:Number, default: 0 },
    three: { type:Number, default: 0 },
    two: { type:Number, default: 0 },
    one: { type:Number, default: 0 },
    total: { type:Number, default: 0 },
  },
  timestamp: { type: Date, default: Date.now },
  phone:{type:String},
  active:{type:Boolean},
  socket_id: String
}
```
## Customer collection
```javascript
{
  _id: {type: ObjectID, unique:true},
  email: {type:String, unique:true},
  password: { type:String },
  name:  String, 
  image: {type:String, default:"default.png"},
  address:   String,
  latitude: {type: Number, default:-1},
  longtitude: {type: Number, default:-1},
  phone: {type:String, unique:true},
  socket_id: String,
  timestamp: { type: Date, default: Date.now }
}
```
## Bill collection
```javascript
{
  _id: {type: ObjectID, unique:true},
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
  store_id: { type: Schema.Types.ObjectId, ref: 'store' },
  total_cost: { type:Number },
  services: [{
    service_id: {type: Schema.Types.ObjectId, ref: "service"},
    quantity: {type:Number, default:1}
  }],
  timestamp: { type: Date, default: Date.now },
  confirm:{type:Boolean, default:false},
  paid: {type:Boolean, default:false},
  coordinate: {
    lat: {type:Number},
    lng: {type:Number}
  },
  address:{type:String}
}
```

## Category
```javascript
{
  _id: {type: ObjectID, unique:true},
  name:  String, 
  timestamp: { type: Date, default: Date.now }
}
```

## City
```javascript
{
  _id: {type: ObjectID, unique:true},
  name: {type:String}
}
```

## Comment
```javascript
{
  _id: {type: ObjectID, unique:true},
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
  store_id: { type: Schema.Types.ObjectId, ref: 'store' },
  rating: { type:Number },
  content:{type:String, default:false},
  timestamp: { type: Date, default: Date.now },
}
```

## Message
```javascript
{
  _id: {type: ObjectID, unique:true},
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
  store_id: { type: Schema.Types.ObjectId, ref: 'store' },
  is_store: { type:Boolean, default:false },
  body: { type:String },
  is_read: {type:Boolean, default:false},
  timestamp: { type: Date, default: Date.now }
}
```


## problems
```javascript
{
  _id: {type: ObjectID, unique:true},
  name: {type:String}
}
```


## Report
```javascript
{
  _id: {type: ObjectID, unique:true},
  content: {type:String},
  store_id: {type: Schema.Types.ObjectId, ref:"store"},
  timestamp: { type: Date, default: Date.now },
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
}
```

## Rescue
```javascript
{
  _id: {type: ObjectID, unique:true},
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
  store_id: { type: Schema.Types.ObjectId, ref: 'store' },
  problem:{type:Schema.Types.ObjectId, ref: 'problem'},
  is_complete: {type:Boolean, default:false},
  coordinate: {
    lat: Number,
    lng: Number
  },
  timestamp: { type: Date, default: Date.now },
}
```

## Service Comment
```javascript
{
  _id: {type: ObjectID, unique:true},
  customer_id: { type: Schema.Types.ObjectId , ref : 'customer'},
  service_id: { type: Schema.Types.ObjectId, ref: 'service' },
  rating: { type:Number },
  content:{type:String, default:false},
  timestamp: { type: Date, default: Date.now },
}
```

## Service
```javascript
{
  _id: {type: ObjectID, unique:true},
  store_id: { type: Schema.Types.ObjectId, ref: 'store' },
  category: { type: Schema.Types.ObjectId, ref: 'Category' },
  image: String,
  description: String,
  name: { type:String },
  price: { type:Number },
  quantity: Number,
  detail: String,
  rating: {
    five: { type:Number, default: 0 },
    four: { type:Number, default: 0 },
    three: { type:Number, default: 0 },
    two: { type:Number, default: 0 },
    one: { type:Number, default: 0 },
    total: { type:Number, default: 0 },
  },
  timestamp: { type: Date, default: Date.now }
}
```

## Sys_user
```javascript
{
  _id: {type: ObjectID, unique:true},
  email: {type:String, unique:true},
  password: { type:String },
  name:  String, 
  phone:{type:String},
  image: { type: String, default : "default_sys.jpg"},
  timestamp: { type: Date, default: Date.now },
}
```
