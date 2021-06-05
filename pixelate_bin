def pixelate_bin(img, window, threshold):
    n, m = img.shape
    n, m = n - n % window, m - m % window
    img1 = np.zeros((n,m))
    for x in range(0, n, window):
        for y in range(0, m, window):
            if img[x:x+window,y:y+window].mean() > threshold:
                img1[x:x+window,y:y+window] = 1
    return img1

# convert image to grayscale
img = np.dot(plt.imread('test.png'), [0.299 , 0.587, 0.114])

fig, ax = plt.subplots(1, 3, figsize=(15,10))

plt.tight_layout()
ax[0].imshow(pixelate_bin(img, 5, .2), cmap='gray')
ax[1].imshow(pixelate_bin(img, 5, .3), cmap='gray')
ax[2].imshow(pixelate_bin(img, 5, .45), cmap='gray')

# remove frames
[a.set_axis_off() for a in ax.flatten()]
plt.subplots_adjust(wspace=0.03, hspace=0)
