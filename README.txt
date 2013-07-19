The OSGDES_Alpha software parses an xml script to generate a 3D environment and events.
A root script ( generally contains script as the first characters in the file name ) contains references to the Event and Environment scripts
for example:



<?xml version="1.0"?>
<Script>
<EnvironmentFileName>Environment0001.xml</EnvironmentFileName>
<EventFileName>Even0001.xml</EventFileName>
</Script>


An example of an environment.xml file

<?xml version="1.0"?>
-<Environment><ActiveGroupIndex>0</ActiveGroupIndex><ActiveViewerIndex>0</ActiveViewerIndex>-<Group><Name>RootGroup</Name>-<Ref><RefName>LightSource0</RefName><EntityType>LightSource</EntityType><RefType>AddChild</RefType></Ref>-<Ref><RefName>PositionAttitudeTransform1</RefName><EntityType>PAT</EntityType><RefType>AddChild</RefType></Ref></Group>-<Viewer><Name>Viewer1</Name><CameraManipulator>OrbitManipulator</CameraManipulator>-<SetUpViewInWindow><x>50</x><y>50</y><width>1024</width><height>768</height></SetUpViewInWindow></Viewer>-<Light><Name>Light0</Name>-<Position><x>2</x><y>2</y><z>2</z><w>1</w></Position>-<Diffuse><x>1</x><y>0</y><z>0</z><w>1</w></Diffuse>-<Specular><x>0</x><y>1</y><z>0</z><w>1</w></Specular>-<Ambient><x>0</x><y>0</y><z>0.2</z><w>1</w></Ambient>-<Direction><x>0.5</x><y>0.5</y><z>-0.5</z></Direction><SetConstantAttenuation>1</SetConstantAttenuation></Light>-<LightSource><Name>LightSource0</Name><SetLocalStateSetModes>ON</SetLocalStateSetModes>-<Ref><RefName>Light0</RefName><EntityType>Light</EntityType><RefType>SetLight</RefType></Ref>-<Ref><RefName>RootGroup</RefName><EntityType>Group</EntityType><RefType>SetStateSetModesOn</RefType></Ref></LightSource>-<Geode><Name>Geode3</Name>-<Cone>-<Center><x>0</x><y>0</y><z>0</z></Center><Height>1</Height><Radius>1</Radius></Cone></Geode>-<PositionAttitudeTransform><Name>PositionAttitudeTransform1</Name>-<Ref><RefName>Geode3</RefName><EntityType>Geode</EntityType><RefType>AddChild</RefType></Ref>-<Position><x>0</x><y>0</y><z>0</z></Position>-<Scale><x>1</x><y>1</y><z>1</z></Scale></PositionAttitudeTransform></Environment>

And an event:


<?xml version="1.0"?>
-<Event><Name>Sequencer1</Name><Type>Sequencer</Type><Subordination>Simultaneous</Subordination>-<Event><Name>Python</Name><Type>Python</Type><Recurrance>Singular</Recurrance>-<Variable><Identifier>Object</Identifier>
<!--<Value>SMTP</Value>-->
<Value>python004</Value></Variable>-<Variable><Identifier>Key</Identifier>
<!--<Value>SMTP</Value>-->
<Value>ex1</Value></Variable></Event></Event>