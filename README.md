<h1>U - Net based Statue object segmentation Research Component</h1>

<p>The customized U – Net Architecture is trained for 200 seated Buddha statue images found on Google, and their corresponding binary masks that to segment the validated user input image. A detailed description of model training has stated in the section 04.02 of submitted EC04 Document.</p>

<h2>Workflow Unit Information</h2>

<table>
    <tr>
        <th>Name of the workflow unit or component</th>
        <td>Segmentation Model</td>
    </tr>
    <tr>
        <th>Objective of the workflow unit or component</th>
        <td>Extract the statue object from the image and removes the background</td>
    </tr>
    <tr>
        <th>Input</th>
        <td>Validated user input image</td>
    </tr>
    <tr>
        <th>Process in Brief</th>
        <td>After the user image is fed to the system as an input, it identifies statue object from the image and creates a binary mask for the object itself. Then subtract the masked area from the original image by leaving a background removed statue object as the output.</td>
    </tr>
    <tr>
        <th>Output</th>
        <td>Validated and background removed user input image</td>
    </tr>
</table>
