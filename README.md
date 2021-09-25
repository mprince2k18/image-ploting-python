# image-ploting-python

            import numpy as np
            import matplotlib.pyplot as plt
            from sklearn.datasets import load_digits
            from sklearn.decomposition import PCA

            digits = load_digits()
            data = digits.data
            data.shape

            #taking a sample image to view
            image_sample = data[0,:].reshape(8,8)

            plt.imshow(image_sample)

![image](https://user-images.githubusercontent.com/43857625/134760211-a816ce2f-596e-4890-a04e-c0450f4eff20.png)


            pca = PCA(2)
            converted_data = pca.fit_transform(digits.data)

            converted_data.shape

            plt.style.use('seaborn-whitegrid')
            plt.figure(figsize = (10,6))
            c_map = plt.cm.get_cmap('jet', 10)
            plt.scatter(converted_data[:, 0], converted_data[:, 1], s = 15,
                        cmap = c_map , c = digits.target)
            plt.colorbar()
            plt.xlabel('PC-1') , plt.ylabel('PC-2')
            plt.show()

![image](https://user-images.githubusercontent.com/43857625/134760217-c41d9f52-ecd7-481b-b6e4-c337ca8528a8.png)
