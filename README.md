# psbuiwebappnodeexpr4
## 5.Routing
```
var bookRouter = app.Router();
app.use('/Books',bookRouter);
bookRouter.route('/single').get(function(req,res){
  res.send();
});
```


##8. Structure and 3rd Party APIs
```
bookRouter.route('/').get(function(req,res){
  var url=''
  mongodb.connect(url,function(err,db){
    var collection = db.collection('books');
    collection.find({}).toArray(
      function(err,res){
        res.render('bookListView',{
          title:'',
          nav:nav
          books:res
        })
      }
    )
  }
})
```
for single book
```
bookRouter.route('/').get(function(req,res){
  var url=''
  var id = new Objectid(req.params.id);
  mongodb.connect(url,function(err,db){
    var collection = db.collection('books');
    collection.findOne({_id:id},
      function(err,res){
        res.render('bookView',{
          title:'',
          nav:nav
          books:res
        })
      }
    )
  }
})
```
