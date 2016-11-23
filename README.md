# dataset_manager
Library to manage a large of projects and datasets.
It allows versionning of the datasets as well tracking of the change of dataset for each project.

If you have many projects with many database, tables, csv to handle for each project,
this is very easy to handle/track/with a minimum amount of code.


Library is available on demand via email or if you have any questions,
feel free.

Project is on BitBucket for current developpers.


Some example of usage:


import project

#------------------ A new Project ---------------------------------
proj1= project.project('daily','marketstore','user_name')
Aptable, Aphisto= proj1.project_export_meta('tuple')   #Export meta data to Pandas

#Add Table using odo pattern URI
proj1.table_add(['yahoo','sqlite:///D://_devs/Python01/aaserialize/store/data1.db', 'Yahoo Datastore db'])
proj1.table_update('yahoo', ['sqlite:///D://_devs/Python01/aaserialize/store/project_reftable.sqlite'])

proj1.table_add('table02', ['sqlite:///D://_devs/Python01/aaserialize/store/project_reftable.sqlite'])
proj1.table_delete('table02')


#Save In Memory data (ie current interpreter in memory data) into a file.
proj1.table_sessiondata_save(globals())


#Export to Python Variable, here Dataframe
dfb= proj1.table_load('yahoo', exportype1='blaze')
dfb.dshape

#Manipulate the variable and do computation
ticker= dfb['daily_us_etf']['sym'].distinct()
ticker1= bz.odo(ticker, pd.DataFrame)


# Commit the Project --------------------------------------------------------
proj1.table_sessiondata_save(globals())  #Resave again the interpreter memory
proj1.project_save()  #Commit the change --> A version is produced


#------------------ Reload Last version--------------------------------------
proj1= project.project(name='daily',folder='marketstore',user='username', version=-1)
Aptable, Aphisto= proj1.project_export_meta('tuple')

proj2.table_sessiondata_load()  #Reload the data of the project in the interpreter







