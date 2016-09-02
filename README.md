# jscience-fix
Just a repository with the jscience library (version 4.3 as base) with quick fixs that I needed

There is a problem in the use of Javolution FastMaps in the Amount class, because the library is not calling FastMap.recycle(obj). 
If this is not called, then when there are MultiClassloader (for example, a server with classloaders per ear, war, jar and server)
the FastMaps could be persisted in the server and a redeploy of an application or a war may fail.
