# OneTab Bot Assets

This directory contains avatar and banner files for the OneTab Discord bot.

## Directory Structure

```
assets/
├── avatars/          # Avatar images for room embeds
└── banners/          # Banner images for room embeds
```

## Usage

### Avatars
- Place avatar images in the `avatars/` folder
- Supported formats: PNG, JPG, JPEG, GIF, WEBP
- Recommended size: 512x512 pixels
- Max file size: 10MB
- Use command: `.t setavatar <filename>`

### Banners
- Place banner images in the `banners/` folder  
- Supported formats: PNG, JPG, JPEG, GIF, WEBP
- Recommended size: 1920x1080 pixels
- Max file size: 10MB
- Use command: `.t setbanner <filename>`

## Examples

```bash
# Set avatar using local file
.t setavatar neural_avatar.png

# Set banner using local file  
.t setbanner quantum_banner.jpg

# Set avatar using URL (still works)
.t setavatar https://example.com/avatar.png

# List available files
.t setavatar
.t setbanner
```

## File Organization Tips

- Use descriptive filenames
- Organize by theme or style
- Keep file sizes reasonable for fast loading
- Test images before deploying to production
