# Flask Blog Application

A full-featured blog application built with Flask, featuring user authentication, profile management, and a clean Bootstrap-based interface.

## Features

- **User Authentication**: Registration, login, and logout functionality
- **User Profiles**: Profile picture upload and account management
- **Blog Posts**: Display blog posts with author information
- **Responsive Design**: Bootstrap 4 powered responsive UI
- **Database Integration**: SQLite database with SQLAlchemy ORM
- **Form Validation**: WTForms with server-side validation
- **Flash Messages**: User feedback system for actions
- **Image Processing**: Automatic image resizing for profile pictures

## Tech Stack

- **Backend**: Flask, Flask-SQLAlchemy, Flask-Login, Flask-Bcrypt
- **Frontend**: HTML5, CSS3, Bootstrap 4, Jinja2 templates
- **Database**: SQLite
- **Image Processing**: Pillow (PIL)
- **Forms**: Flask-WTF, WTForms

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Flask_Blog
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask flask-sqlalchemy flask-bcrypt flask-login flask-wtf pillow
   ```

4. **Run the application**
   ```bash
   python run.py
   ```

5. **Access the application**
   Open your browser and go to `http://localhost:5000`

## Database Setup

The application uses SQLite and will automatically create the database file (`site.db`) when you first run the application. The database includes two main tables:

- **Users**: Stores user account information
- **Posts**: Stores blog post information

## Routes

- `/` or `/home` - Homepage displaying blog posts
- `/about` - About page
- `/register` - User registration
- `/login` - User login
- `/logout` - User logout
- `/account` - User account management (requires login)

## Forms

### Registration Form
- Username (unique, 2-20 characters)
- Email (unique, valid email format)
- Password (with confirmation)

### Login Form
- Email
- Password
- Remember Me option

### Update Account Form
- Username (unique validation)
- Email (unique validation)
- Profile picture upload (jpg, png only)

## Styling

The application uses a custom Bootstrap 4 theme with:
- Steel blue navigation bar (`bg-steel`)
- Responsive grid layout
- Custom CSS for blog posts and user profiles
- Mobile-friendly design

## Security Features

- Password hashing using Flask-Bcrypt
- CSRF protection on all forms
- Login required decorators for protected routes
- Form validation with WTForms
- SQL injection prevention through SQLAlchemy ORM

## Customization

### Adding New Routes
Add new routes in `flaskblog/routes.py`:
```python
@app.route("/new-route")
def new_route():
    return render_template('new_template.html', title='New Page')
```

### Modifying Styles
Edit `flaskblog/static/main.css` to customize the appearance.

### Changing Database Models
Modify the models in `flaskblog/models.py` and run:
```python
from flaskblog import db
db.create_all()
```

## Troubleshooting

### CSS Not Loading
- Ensure you're running the app from the correct directory
- Try a hard refresh (Ctrl+F5)
- Check browser developer console for 404 errors

### Database Issues
- Delete `instance/site.db` to reset the database
- Ensure all models are properly defined

### Image Upload Issues
- Ensure the `static/profilepics` directory exists
- Check file permissions for the static directory

## Future Enhancements

- Add blog post creation functionality
- Implement comment system
- Add post categories/tags
- Implement search functionality
- Add email notifications
- Implement password reset functionality
- Add social media integration

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the MIT License.

## Author
**Venkata Mastan Mudigonda**
Developed as a Flask learning project.

---

**Note**: This is a development project. For production use, ensure you:
- Use environment variables for secret keys
- Set up proper database backups
- Implement rate limiting
- Use HTTPS
- Set up proper logging and monitoring