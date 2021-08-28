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
description: このBackup-CcCertificationAuthorityコマンドレットは、Skype for Business クラウド コネクタ エディション証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの CA フォルダーに保存します。
ms.openlocfilehash: f7803a1c773ca3561b13ef5a263002cc4b8e049a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582531"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
このBackup-CcCertificationAuthorityコマンドレットは、Skype for Business クラウド コネクタ エディション証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの CA フォルダーに保存します。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの CA フォルダーに保存します。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

証明機関のバックアップは、障害が発生した場合に同じ証明書を持つクラウド コネクタ アプライアンスを再展開する場合、またはアプライアンスを新しいハードウェアに移動する場合に役立ちます。 このコマンドは、クラウド コネクタ証明機関サービスのコピーを ADサーバーから \<SiteRootDirectory\> "\CA\SfB CCE Root.p12" に保存します。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このBackup-CcCertificationAuthorityは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

