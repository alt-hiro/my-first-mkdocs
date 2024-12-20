# mypage
おはよう


!!! note
    note のサンプル表示.
    なにか特筆すべきトピックのとき使う

!!! note "ここ気をつけてね"
    note のなかで改行したい場合.<br>
    br タグを使う
    
!!! warning
    ここ気を付けて！とかそういったときに使う

code block を書いてみる
```shell
ls
python pip install dbt-snowflake
```

こんどはタブっぽく

=== "Latest"

    ```sh
    pip install mkdocs-material
    ```

=== "9.x"

    ```sh
    pip install mkdocs-material=="9.*" # (1)!
    ```

ほげ、だめだった

!!! tip

    If you don't have prior experience with Python, we recommend reading
    [Using Python's pip to Manage Your Projects' Dependencies], which is a
    really good introduction on the mechanics of Python package management and
    helps you troubleshoot if you run into errors.



こういう書き方もできる
??? question "How to add plugins to the Docker image?"

    Material for MkDocs only bundles selected plugins in order to keep the size
    of the official image small. If the plugin you want to use is not included,
    you can add them easily:

    === "Material for MkDocs"

        Create a `Dockerfile` and extend the official image:

        ``` Dockerfile title="Dockerfile"
        FROM squidfunk/mkdocs-material
        RUN pip install mkdocs-macros-plugin
        RUN pip install mkdocs-glightbox
        ```

    === "Insiders"

        Clone or fork the Insiders repository, and create a file called
        `user-requirements.txt` in the root of the repository. Then, add the
        plugins that should be installed to the file, e.g.:

        ``` txt title="user-requirements.txt"
        mkdocs-macros-plugin
        mkdocs-glightbox
        ```

??? tip "How to integrate with third-party JavaScript libraries"

    It is likely that you will want to run your JavaScript code only
    once the page has been fully loaded by the browser. This means
    installing a callback function subscribing to events on the
    `document$` observable exported by Material for MkDocs.
    Using the `document$` observable is particularly important if you
    are using [instant loading] since it will not result in a page
    refresh in the browser - but subscribers on the observable will be
    notified.

    ``` javascript
    document$.subscribe(function() {
      console.log("Initialize third-party libraries here")
    })
    ```

    `document$` is an [RxJS Observable] and you can call the `subscribe()`
    method any number of times to attach different functionality.

  [instant loading]: setup/setting-up-navigation.md/#instant-loading
  [RxJS Observable]: https://rxjs.dev/api/index/class/Observable