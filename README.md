# Small PHP-CS-Fixer Docker image

This image uses Wolfi-OS to create a very small PHP-CS-Fixer Docker image and still glibc, to be used in CI/CD pipelines.

- Official PHP-CS-Fixer image is 100MB and uses Alpine Linux (is musl and does sometimes work **different** than your local machine)
- This image is 41MB and uses Wolfi OS (is glibc and works the same as your regular local machine)

## Usage

```bash
# or alternative use ghcr.io/shyim/php-cs-fixer:latest
docker run --rm -v $(pwd):$(pwd) -w $(pwd) shyim/php-cs-fixer:latest --rules @PER-CS2.0,@PER-CS2.0:risky --allow-risky=yes .
```

If you don't want to pass the as arguments, you can create your regular `.php-cs-fixer.php` file and PHP-CS-Fixer will pick it up as usual.
