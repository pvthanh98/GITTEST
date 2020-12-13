# NOTHING SPECIAL

```json
{
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
