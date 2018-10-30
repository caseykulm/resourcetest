# Resource linking test

1. When tv1 was put in the layout first,
    1. with tv1 defining constraints with `@+id/tv2`, and tv2 using `android:id=@+id/tv2`
        * Result: Everything works
    2. with tv1 defining constraints with `@+id/tv2`, and tv2 using `android:id=@id/tv2`
        * Result: Editor isn't happy, but everything works
    3. with tv1 defining constraints with `@id/tv2`, and tv2 using `android:id=@+id/tv2`
        * Result: Everything works
    4. with tv1 defining constraints with `@id/tv2`, and tv2 using `android:id=@id/tv2`
        * Result: Build fails with AAPT2 linking error
2. When tv2 was put in the layout first,
    1. with tv1 defining constraints with `@+id/tv2`, and tv2 using `android:id=@+id/tv2`
        * Result: Everything works
    2. with tv1 defining constraints with `@+id/tv2`, and tv2 using `android:id=@id/tv2`
        * Result: Editor isn't happy, but everything works
    3. with tv1 defining constraints with `@id/tv2`, and tv2 using `android:id=@+id/tv2`
        * Result: Everything works
    4. with tv1 defining constraints with `@id/tv2`, and tv2 using `android:id=@id/tv2`
        * Result: Build fails with AAPT2 linking error
        

## To test

To test yourself go into the `activity_main.xml` and comment out the default case, and uncomment 
the case you want to test.

## Overall Results

* Order does not matter
* `android:id` should use `@+id` to keep the editor happy
* `@+id` must exist somewhere in the layout