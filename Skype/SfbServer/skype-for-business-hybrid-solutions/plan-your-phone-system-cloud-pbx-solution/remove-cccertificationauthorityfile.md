---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: このRemove-CcCertificationAuthorityFileコマンドレットは、サイト共有ディレクトリの下にある CA フォルダー内の証明機関サービス バックアップ ファイルを削除Skype for Business クラウド コネクタ エディション。
ms.openlocfilehash: 93141fee2ab2bf5af4ac826f4926523bd26e9e45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624989"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
Remove-CcCertificationAuthorityFile コマンドレットは、証明機関サービス のバックアップ ファイル &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" を、Skype for Business クラウド コネクタ エディション のサイト共有ディレクトリの CA フォルダーから削除します。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、サイト共有ディレクトリの CA フォルダーの証明機関サービス バックアップ ファイル &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" を削除します。
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このRemove-CcCertificationAuthorityFileは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

