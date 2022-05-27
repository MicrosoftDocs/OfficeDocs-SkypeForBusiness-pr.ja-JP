---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority コマンドレットは、Skype for Business クラウド コネクタ エディション証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの下の CA フォルダーに保存します。
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675459"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Backup-CcCertificationAuthority コマンドレットは、Skype for Business クラウド コネクタ エディション証明機関サービスをファイルにバックアップします。 また、このコマンドレットは、サイト共有ディレクトリの下の CA フォルダーにも保存します。

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>パラメーター

なし

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの下の CA フォルダーに保存します。

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

証明機関のバックアップは、同じ証明書を使用して Cloud Connector アプライアンスを再デプロイする場合に役立ちます。 例として以下のようなものがあります。

- ディザスター リカバリー。
- アプライアンスを新しいハードウェアに移動します。

このコマンドは、AD Server から Cloud Connector 証明機関サービスのコピーを保存します `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`。

## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Backup-CcCertificationAuthority コマンドレットでは、パイプライン化された入力は受け入れられません。

## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

None

## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  