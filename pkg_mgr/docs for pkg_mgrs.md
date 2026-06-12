# Commands for pkg mgrs

## Building

### Windows

#### Winget

```
install from manifest
```

#### Scoop:

```
install from .json
```

#### Choco:

```
choco pack .\uniplan.nuspec
```

### Linux

#### Flatpak:

```
flatpak-builder --force-clean build-dir org.dstudios.uniplan.yml
```

#### Snapcraft:

```
snapcraft pack
```

#### Arch:

```

```

#### Void:

```
./xbps-src pkg uniplan
```

## Installing from build

### Windows

#### Winget

```
winget install --manifest .\manifests\d\dstudios\uniplan\0.0.1
```

#### Scoop:

```
scoop install .\uniplan.json
```

#### Choco:

```
choco install uniplan -y --source="."
```

### Linux

#### Flatpak:

```
flatpak-builder --user --install --force-clean build-dir org.dstudios.uniplan.yml
```

#### Snapcraft:

```
sudo snap install ./uniplan.snap --dangerous
```

#### Arch:

```

```

#### Void:

```
sudo xbps-install --repository $(pwd)/hostdir/binpkgs/nonfree uniplan
```

## Removing

### Windows

#### Winget

```
winget uninstall dStudios.UniPlan
```

#### Scoop:

```
scoop uninstall uniplan
```

#### Choco:

```
choco uninstall uniplan -y
```

### Linux

#### Flatpak:

```
flatpak uninstall org.dstudios.uniplan.yml
```

#### Snapcraft:

```
sudo snap remove uniplan
```

#### Arch:

```
sudo pacman -R uniplan
```

#### Void:

```
sudo xbps-remove -y uniplan
```
