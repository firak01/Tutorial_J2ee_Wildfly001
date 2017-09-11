	
	FGL: 20170911
	Nach einem Neustart des Servers die Datenquelle DefaultDS erst entfernen und dann wieder neu anlegen:
	
	------------------------------------------------------------------------
	Starte den Wildfly Server per Batch.
	Deploye den JDBC Treiber per AdminConsole  unter localhost:8080 (Reiter Deployments), damit er beim Erstellen der Datenquelle zur Verfügung steht.
	Mit dem Pfad zu hsqldb - jar Datei: C:\Server\hsqldb\lib\hsqldb.jar 
	 
	Lege per AdminConsole unter localhost:8080 (Reiter Configuration) eine Datenquelle DefaultDS an.
	für hsqldb.jar
	Mit JNDI Name: java:/DefaultDS
	Connection: jdbc:hsqldb:${jboss.server.data.dir}${/}hypersonic${/}localDB;shutdown=true
	Username: sa
	
	Anschliessend muss diese Datenbquelle noch "enabled" werden.
	
	Beende den Wildfly Server
	--------------------------------------------------------
	
	Nun muss die Applikation deployed werden.
	Starte den Wildfly Server in Eclipse.
	Füge die Anwendung "Library" per Rechstclick auf den Servereintrag mit "Add and Remove.." hinzu.
	
	---------------------------
	
	Erreichbar ist die Anwendung dann über die URL: http://localhost:8080/Library-Web/
	