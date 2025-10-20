# WorkforceTracker

A comprehensive workforce management system built with ASP.NET Core MVC that allows you to track employee information and work shifts efficiently.

## Features

### Employee Management
- **Add/Edit/Delete Employees**: Complete CRUD operations for employee records
- **Employee Search**: Search employees by name, job title, or department
- **Pagination**: Efficient browsing through large employee lists
- **Employee Details**: View detailed employee information including work history

### Work Shift Management
- **Shift Tracking**: Record daily work shifts for each employee
- **Shift Types**: Support for different shift types (day shift, night shift, etc.)
- **Attendance Status**: Track presence/absence for each shift
- **Overtime & Underwork**: Monitor overtime hours and underwork situations
- **Commute Details**: Record transportation and commute information
- **Persian Date Support**: Built-in support for Persian calendar dates

### Key Features
- **Modern UI**: Clean, responsive interface built with Bootstrap
- **Database Support**: SQL Server and SQLite database support
- **Entity Framework Core**: Modern ORM for data management
- **Validation**: Comprehensive input validation and error handling
- **Multi-language Support**: Persian language support for dates and interface

## Technology Stack

- **.NET 8.0**: Latest .NET framework
- **ASP.NET Core MVC**: Web application framework
- **Entity Framework Core 9.0**: Object-relational mapping
- **SQL Server**: Primary database (with SQLite fallback)
- **Bootstrap**: Frontend CSS framework
- **PersianDate**: Persian calendar support

## Prerequisites

- .NET 8.0 SDK or later
- SQL Server (or SQLite for development)
- Visual Studio 2022 or VS Code (recommended)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/WorkforceTracker.git
   cd WorkforceTracker
   ```

2. **Restore dependencies**
   ```bash
   dotnet restore
   ```

3. **Update connection string**
   
   Edit `appsettings.json` to configure your database connection:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=your_server;Database=WorkforceTracker;Trusted_Connection=true;TrustServerCertificate=true;"
     }
   }
   ```

4. **Run database migrations**
   ```bash
   dotnet ef database update
   ```

5. **Run the application**
   ```bash
   dotnet run
   ```

6. **Access the application**
   
   Open your browser and navigate to `https://localhost:5001` (or the URL shown in the console)

## Usage

### Managing Employees

1. **Add New Employee**
   - Navigate to "Employees" from the main menu
   - Click "Create New" button
   - Fill in employee details (name, job title, department, contact info)
   - Click "Create" to save

2. **Search Employees**
   - Use the search box on the employees page
   - Search by first name, last name, job title, or department

3. **Edit Employee**
   - Click "Edit" next to any employee
   - Modify the information and save changes

### Managing Work Shifts

1. **Add Work Shift**
   - Go to an employee's detail page
   - Click "Add Work Shift"
   - Fill in shift details:
     - Date and day of week
     - Start and end times
     - Shift name and status
     - Overtime/underwork hours (if applicable)
     - Commute details
   - Save the shift

2. **View Work History**
   - Employee detail pages show all work shifts
   - Work shifts page shows all shifts across all employees

## Database Schema

### Employee Table
- `Id`: Primary key
- `FirstName`: Employee's first name
- `LastName`: Employee's last name
- `JobTitle`: Position/title
- `Department`: Department/division
- `Phone`: Contact phone number
- `Email`: Email address

### WorkShift Table
- `Id`: Primary key
- `EmployeeId`: Foreign key to Employee
- `Status`: Shift status (Present/Absent)
- `ShiftName`: Name of the shift
- `DayOfWeek`: Day of the week
- `Date`: Shift date
- `StartTime`: Shift start time
- `EndTime`: Shift end time
- `CommuteDetails`: Transportation information
- `IsPresent`: Boolean presence indicator
- `HasOvertime`: Overtime flag
- `OvertimeHours`: Overtime duration
- `HasUnderwork`: Underwork flag
- `UnderworkHours`: Underwork duration

## Configuration

### Database Configuration
The application supports both SQL Server and SQLite databases. Configure your preferred database in `appsettings.json`:

**SQL Server:**
```json
"DefaultConnection": "Server=localhost;Database=WorkforceTracker;Trusted_Connection=true;TrustServerCertificate=true;"
```

**SQLite:**
```json
"SQLiteConnection": "Data Source=workforcetracker.db"
```

### Persian Date Support
The application includes Persian calendar support. Set `UsePersianDates` to `true` in `appsettings.json` to enable Persian date formatting.

## Development

### Running in Development Mode
```bash
dotnet run --environment Development
```

### Adding New Migrations
```bash
dotnet ef migrations add MigrationName
```

### Updating Database
```bash
dotnet ef database update
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

If you encounter any issues or have questions, please:
1. Check the [Issues](https://github.com/yourusername/WorkforceTracker/issues) page
2. Create a new issue with detailed description
3. Contact the development team

## Changelog

### Version 1.0.0
- Initial release
- Employee management (CRUD operations)
- Work shift tracking
- Persian date support
- SQL Server and SQLite database support
- Bootstrap-based responsive UI

---

**Note**: Remember to update the GitHub repository URL in this README with your actual repository URL before publishing.
