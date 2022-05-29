# wordpress-hardenning

```
find . -type d  -print0 | xargs -0 chmod 755
```

```
find . -type f -name '*.php' -print0 | xargs -0 chmod 644
```

```
find . -type f -name 'wp-config.php' -print0 | xargs -0 chmod 440
```

```
find . -type f -name '.httpaccess' -print0 | xargs -0 chmod 440
```

```
find ./ -type f \( -iname \*.jpg -o -iname \*.png \)
```
