  users.html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Bootstrap CSS -->
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-10 text-center">
        <h1>Users List</h1>
        <table class="table table-hover">
            <thead>
                <tr>
                    <th scope="col">S.No</th> <!-- Index column -->
                    <th scope="col">Username</th>
                    <th scope="col">Email</th>
                    <th scope="col">Role</th>
                    <th scope="col">Action</th>
                </tr>
            </thead>
            <tbody>
                {% for i in data %}  <!-- Displaying user information from the data variable -->
                <tr>                   
                    <th scope="row">{{ i.id }}</th> 
                    <td>{{ i.username }}</td> <!-- Use 'username' from the User model -->
                    <td>{{ i.email }}</td>
                    <td>
                        {% if i.is_staff %}
                            Admin
                        {% else %}
                            User
                        {% endif %}
                    </td>
                    <td>
                         <a href="{% url 'edituser' i.id %}" class="btn btn-warning btn-sm float-right">Edit</a> 
                         <a href="{% url 'delete' i.id %}" class="btn btn-danger btn-sm">Delete</a>
                    </td>
                </tr>
                {% endfor %}
            </tbody>
        </table>
    </div>
</body>
</html> 
