# Meet the Pre-Requisites
# --------------------------
## Connect to Postgresql database
![Alt text](/screen_shots/Screenshot_Lab1_1.png?raw=true "Simple Code on IPython Notebooks")

## Verify whether sample database exists and if not create one
![Alt text](/screen_shots/Screenshot_Lab1_2.png?raw=true "Simple Code on IPython Notebooks")

## Load the data in sample database
![Alt text](/screen_shots/Screenshot_Lab1_3.png?raw=true "Simple Code on IPython Notebooks")

## verify metadata definition of table
![Alt text](/screen_shots/Screenshot_Lab1_4.png?raw=true "Simple Code on IPython Notebooks")

# ************************************Lets now begin with Sqoop operations *********************************

[root@hadoop ~]# sqoop import --connect jdbc:postgresql://localhost/dvdrental --username postgres -P --split-by actor_id --columns actor_id,first_name,last_name,last_update --table actor --target-dir /opt/sqoop/hivetable --hive-import --create-hive-table --hive-table actor -m 1 <br>

##  For non-root sudoer execution <br>
### Goto $SQOOP_HOME/bin <br> 
[hdeveloper@hadoop bin]$ sudo  ./sqoop import --connect jdbc:postgresql://localhost/dvdrental --username postgres -P --split-by actor_id --columns actor_id,first_name,last_name,last_update --table actor --target-dir /opt/sqoop/hivetable --hive-import --create-hive-table --hive-table actor -m 1 <br>

