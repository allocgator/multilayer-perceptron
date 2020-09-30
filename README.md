# Multi-Layer Perceptron

This project uses the [Keras] library and the extended MNIST [EMNIST] dataset of handwritten digits. This dataset​ expands on the original MNIST, adding handwritten letters as well as additional samples of handwritten digits. There are several "splits" of the data by various characteristics. This project uses the "EMNIST Letters" dataset in particular, which contains data split into 26 classes, one for each letter in the English alphabet.

# More on the Dataset
[​Matlab format dataset​] is downloaded and extracted, and from it the file `​matlab/emnist-letters.mat​` is used. This dataset folds together both upper- and lowercase letters into a single class. The `​data['mapping']`​ field maps from class numbers to ASCII codes of their corresponding letters. For example, class 1 maps to ASCII codes 65 and 97 (`​'A'`​ and `​'a'`​). This may affect network design. The dataset can be reshaped into either a 2D array of size 28x28 or 1D array of size 784. The data is already split into *training* and *test* sets. *Validation* set is obtained from the *training* set. More details on [EMNIST Paper].

# An MLP for EMNIST Letters

Since the EMNIST Letters data has 26 classes and mixes upper- and lowercase letters within each class, a network architecture consisting of three layers - input, hidden, and output, with a batch size of 128, number of classes as 26, and number of epochs as 20 is evaluated.

This architecture is evaluated using different activation functions like **ReLU**, **Softmax**, **tanh**, and **Sigmoid**, with *early stopping* and *L2 regularization* with 2048 neurons, and other additonal parameters described in the Jupyter notebook.

# Dual-booting Ubuntu and Windows

Using a GPU significantly reduces compute time per epoch. This is going to be crucial in the next project. The below setup ensures groundwork for the next project. **Ubuntu is going to be installed on a separate partition**

+ Turn off hibernate:

  Admin cmd > `powercfg -hibernate off`

+ Disabe fast startup:
  + Control Panel > Power Options > (Uncheck) Turn on fast startup
  + Ensured no row under "On battery" and "Pluged in" is set to Hibernate

+ Shrink Volume of C: using the *Disk Management* utility in Windows

+ Shutdown PC and enter machine's BIOS utility (Enter / F12 at boot logo)
  + Disable Secure Boot
  + Save changes and restart

+ Prepare USB:
  + Download Rufus and select the .iso
  + Use GPT partitioning for UEFI (and MBR for BIOS)

+ Installation type:
  + Partition: Primary
  + Location : Beginning of this space
  + Use as   : Ext 4 journaling file system
  + Mount point: /
  + Device for boot loader information: System SSD


[Keras]: https://keras.io
[EMNIST]: https://www.nist.gov/itl/products-and-services/emnist-dataset
[EMNIST Paper]: https://arxiv.org/abs/1702.05373
[​Matlab format dataset​]: http://www.itl.nist.gov/iaui/vip/cs_links/EMNIST/matlab.zip
