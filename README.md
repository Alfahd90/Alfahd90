DefinitionFile definitionFile = revitApp.OpenSharedParameterFile();
DefinitionGroups definitionGroups = definitionFile.Groups;

// Iterate through the definition groups to find the desired shared parameters
foreach (DefinitionGroup group in definitionGroups)
{
    // Iterate through the definitions within each group
    foreach (Definition definition in group.Definitions)
    {
        // Retrieve the necessary parameter information (name, data type, etc.)
        string parameterName = definition.Name;
        // ...
        // Perform any additional processing or store the parameter information as needed
    }
}
// Example of exporting to a CSV file
using (StreamWriter writer = new StreamWriter("shared_parameters.csv"))
{
    // Write the header row
    writer.WriteLine("Parameter Name, Data Type");

    // Iterate through the shared parameter definitions and write the data
    foreach (Definition definition in sharedParameterDefinitions)
    {
        string parameterName = definition.Name;
        string dataType = definition.ParameterType.ToString();

        // Write the parameter information to the CSV file
        writer.WriteLine($"{parameterName}, {dataType}");
    }
}
