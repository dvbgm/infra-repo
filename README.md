# infra-repo
## В этом репозитории описана конфигурация как flux слушает репозитории

- **`apps/`** - конфигурация подключенного репозитория с приложениями
- **`flux-system/`** - конфигурация FluxCD (создана при bootstrap)
- **`kustomization.yaml`** - главный файл, описывающий все ресурсы для работы FluxCD

### Установка FluxCD и проверка работы

__команда установки__
```bash
flux bootstrap github \
  --token-auth=true \
  --owner=dvbgm \
  --repository=infra-repo \
  --branch=main \
  --path=clusters/my-cluster \
  --personal
```

__Команда проверки работы и синхронизации__
```bash
flux get sources git

flux get kustomizations
```