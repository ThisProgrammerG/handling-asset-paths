# handling-asset-paths
Example of handling asset paths
```
from pathlib import Path


assets_path = Path().cwd()

# Parameters hardcoded for intellisense.
def get_path(*, fonts: str = '', images: str = '', musics: str = '', sounds: str = '') -> Path:
    directory_name, file_name = next(((k, v) for k, v in locals().items() if v), (None, None))
    if not file_name:
        raise ValueError(f'Missing file name.')
    return assets_path / directory_name / file_name

print(get_path(fonts='supertastic.ttf'))
print(get_path(images='field_of_stars.png'))
print(get_path(musics='boss_fight.wav'))
print(get_path(sounds='bubble_pop.ogg'))
print(get_path(images='wolves/big_bad_wolf.png'))

```
