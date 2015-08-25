# node-search-in-directory

指定ディレクトリ内のファイルをスキャンし、文字列を検索します。

## Usage

```js
var SearchInDir = require('node-search-in-directory');

var searchInDir = new SearchInDir(
	[
		'/path/to/target/**/*' // <- use glob format.
	] ,
	{
		'keyword': 'test', // <- keyword (string)
		'filter': [
			/./i // <- path filters (RegExp)
		] ,
		'ignore': [
			/deep/ // <- ignore path filters (RegExp)
		] ,
		'allowRegExp': false,
		'ignoreCase': false,
		'matchFileName': false,
		'progress': function( done, max ){
			console.log( done +'/'+ max + ' done.' );
		} ,
		'match': function( file, result ){
			console.log('matche: ' + file);
			console.log(result);
		} ,
		'unmatch': function( file, result ){
			console.log('unmatch: ' + file);
			console.log(result);
		} ,
		'error': function( file, error ){
			console.log('error: ' + file);
			console.log(result);
		} ,
		'complete': function(){
			console.log('all done!');
		}
	}
);
```

## License

MIT
