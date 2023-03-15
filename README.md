### 使用
    . 在Application中初始化
        '''java
            val loaderConfig = ImageLoaderConfig.Builder(LoaderEnum.GLIDE, GlideImageLocader())
            .build()

            ImageLoaderManager.getInstance().init(this, loaderConfig)
        '''
    . 加载图片
        '''java
            ImageLoaderManager
            .getInstance()
            .showImage(
                ImageLoaderOptions.Builder(imageView!!, url2)
                    .isSkipMemoryCache(true) //                                .placeholder()
                    .setOnProgressListener(OnProgressListener { imageUrl, bytesRead, totalBytes, isDone, exception ->
                        if (totalBytes == 0L) {
                            return@OnProgressListener
                        }
                        if (isDone) {

                            println("图片加载完成")
                        }
                val format =
                    String.format("wxy 加载进度：%.2f %% %n", bytesRead * 100f / totalBytes)
                    //                                        System.out.println(format);
                    Log.d("MainActivity", format)
                    })
                    .build()
                )
        '''