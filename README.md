# psbuiwebappnodeexpr4
## 5.Routing
```
var bookRouter = app.Router();
app.use('/Books',bookRouter);
bookRouter.route('/single').get(function(req,res){
  res.send();
});
```
