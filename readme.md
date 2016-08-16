# Boilerplate for Laravel Web Application

This Boilerplate include basic front end library such as jQuery, Bootstrap and Font Awesome.

Other than that, Laravel package included is Laratrust - used for ACL, Collective - a Form Helpers.

## Installation

Run the following command

	composer create-project nasrulhazim/boilerplate-laravel your-project-name

If you were asked to remove Git history, just choose `Y`.

## Configuration

Open `.env` and configure your database name, username and password

Run the following command to setup the database tables and seeding default ACL

	php artisan migrate && php artisan db:seed

You may run `php artisan serve` to start using the Boilerplate for Laravel Web Application

## Blade Template

### Styling

You may add more styles by adding using `@section('css')`. Sample usage

	@section('css')
	<style>
		p {
			color: green;
		}
	</style>
	@endsection

OR

	@section('css')
		 <link rel="stylesheet" type="text/css" href="{{ url('some/css/path/to/desired.css') }}">
	@endsection

### JavaScript

You may add more JavaScript by adding using `@section('script')`. Sample usage

	@section('script')
	<script>
		$().ready(function(){
			// do your stuff here
		});
	</script>
	@endsection

OR

	@section('script')
		 <script src="{{ url('some/js/path/to/desired.js') }}"></script>
	@endsection

## Others

### Configure Project's Information

If you want to set set your project configuration like project's name, you can set in `config/project.php`.

You may add something like

```php
return [
	'name' => 'My Project Name',
	'email' => [
		'admin' => 'admin@project.com',
		'support' => 'support@project.com',
		'feedback' => 'feedback@project.com'
	]
];
```

Later you may access to your configuration using Laravel helper `config()`. You may access support email by calling:

```php
config('project.email.support');
```

### Create a delete link

You may use `js/delete.js` if you want to have prompt message upon delete a record.

Include the `js/delete.js` in your view

	<script type="text/javascript" src="{{ url('js/delete.js') }}"></script>

Usage example

	<a href="posts/2" data-method="delete" data-token="{{csrf_token()}}"> 

Or, request confirmation in the process

	<a href="posts/2" data-method="delete" data-token="{{csrf_token()}}" data-confirm="Are you sure?">



