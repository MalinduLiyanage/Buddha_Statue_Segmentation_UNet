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

<h2>Summary of the Trained U-Net Model</h2>

<table>
    <tr>
        <th>Model Component</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>Input Layer</td>
        <td>The input layer takes in images of size 256×256×1</td>
    </tr>
    <tr>
        <td>Encoder</td>
        <td>
            <ul>
                <li>Consists of 4 blocks of convolutional layers with ReLU activation function and "Same" padding. Kernel size is 3×3.</li>
                <li>Each block has two convolutional layers followed by a max-pooling layer. Kernel size is 2×2.</li>
                <li>The number of filters in the convolutional layers increases when reaching the bottleneck. (From 64 to 512)</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Bottleneck</td>
        <td>Contains two convolutional layers with 1024 filters each.</td>
    </tr>
    <tr>
        <td>Decoder</td>
        <td>
            <ul>
                <li>Consists of 4 blocks of transposed convolutional layers (for up sampling) followed by two convolutional layers</li>
                <li>The output of the transposed convolutional layers is concatenated with the corresponding feature map from the encoder path.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Output Layer</td>
        <td>A single convolutional layer with a sigmoid activation function with same spatial dimensions for input layer.</td>
    </tr>
    <tr>
        <td>Optimizer</td>
        <td>Adam optimizer with learning rate of 1e-4</td>
    </tr>
    <tr>
        <td>Loss Function</td>
        <td>Binary - Cross entropy</td>
    </tr>
    <tr>
        <td>Trained Epochs</td>
        <td>100</td>
    </tr>
    <tr>
        <td>Early stopping</td>
        <td>Enabled. The best model is found on the 74th Epoch</td>
    </tr>
    <tr>
        <td>Platform</td>
        <td>Google Colab, with T4 GPU enabled.</td>
    </tr>
</table>

