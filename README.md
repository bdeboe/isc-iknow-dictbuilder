# iKnow Dictionary Builder

This demo application is meant to illustrate *data-driven modelling*, how you can use iKnow to build or refine a dictionary / taxonomy, demonstrating how our bottom-up approach complements top-down knowledge. It features a simple drag-and-drop GUI in which you can explore the entities in your domain (top/similar entities) and select the ones you wish to assign to your dictionaries (or blacklist).


### Installation notes
* Import associated code
* Create a REST handler web application by invoking Demo.DictionaryBuilder.Utils:CreateRestWebApp() in your namespace of choice
* Access the application through http://localhost:_port_/csp/_namespace_/DictionaryBuilder.csp?_123_ where _123_ is the ID of the domain in which you wish to work


### Other notes
* If you're working with a domain that's being managed by a domain definition, take note of the following
 * You can only modify your dictionary contents if the _allowCustomUpdates_ attribute of your &lt;domain&gt; element is set to true
 * By default, rebuilding a domain will wipe its dictionaries and recreate them based on the contents of the &lt;matching&gt; element. To preserve your work in the DictionaryBuilder GUI, make sure to set its _dropBeforeBuild_ attribute to false


### TODO
* add reload / reset button
* clean up deleted terms, items and dictionaries as part of RestHandler:UpdateDictionaries()
* nicen async re-matching as part of RestHandler:UpdateDictionaries() (currently just jobs this off, with no response to the client when it's done)
