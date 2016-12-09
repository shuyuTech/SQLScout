# SQLScout
2.0.7/SQLScout.jar Replace `/home/liuhuan/.AndroidStudio2.2/config/plugins/SQLScout/lib/SQLScout.jar`

//具体破解的介绍Blog: <http://www.cnblogs.com/tiantianbyconan/p/5972138.html>


Connecting to Android Databases
To connect to a database in an Android device (including the Android emulator), your project must be an Android application and it must be running on the emulator or a real device.
Live Device Connection
This is a new feature introduced in SQLScout 2.0 that allows you to connect, manage and update databases in your Android device, in real time.
One-time setup:
Note: SQLScout 2.0.6 (or newer) requires sqlscout-server 2.0 (or newer.)
Add IDEScout's Maven repository to the top-level build.gradle file in your project:
  allprojects {
      repositories {
          jcenter()
          maven {
              url 'http://www.idescout.com/maven/repo/'
          }
      }
  }
Add com.idescout.sql:sqlscout-server:2.0 as a dependency to your project's app module:
  compile 'com.idescout.sql:sqlscout-server:2.0'
In the onCreate method of your main Activity invoke the method com.idescout.sql.SqlScoutServer#create as follows:
  @Override
  public void onCreate(Bundle savedInstanceState) {
    SqlScoutServer.create(this, getPackageName());
To create a "live device connection":
Click the "Add" action in the SQLite Explorer and select "Android (Live Device Connection)" (see figure 1). The "New Android SQLite Data Source" dialog will appear (see figure 2).
Enter the name of the Data Source. Please note that this is a logical name for the database connection and not the name of the database itself.
Select the device from the "Device" drop-down. An empty drop-down means that there are not any running Android devices connected to the IDE.
Select the package name (or application ID) from the "Package name" drop-down. The drop-down only includes packages (or application IDs) that contain a database.
Select the type of storage: internal or external memory of the device or emulator.
Select the SQLite database from the "Database" drop-down.
Click "OK".
