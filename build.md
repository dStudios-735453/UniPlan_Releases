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
sudo snap install ./x.snap --dangerous
```

#### Arch:

```

```

#### Void:

```

```
