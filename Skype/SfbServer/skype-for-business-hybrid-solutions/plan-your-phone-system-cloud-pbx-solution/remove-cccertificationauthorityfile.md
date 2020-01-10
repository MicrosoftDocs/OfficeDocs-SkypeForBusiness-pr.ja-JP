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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector エディションのサイト共有ディレクトリの CA フォルダーにある証明機関サービスのバックアップファイルが削除されます。
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003297"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector&lt;エディション&gt;のサイト共有ディレクトリの下にある CA フォルダーで、証明機関サービスのバックアップファイル "SiteRootDirectory \CA\SfB CCE Root. p12" が削除されます。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、サイトの共有ディレクトリの&lt;下&gt;にある CA フォルダーの証明機関サービスバックアップファイル "SiteRootDirectory \CA\SfB CCE ルート. p12" を削除します。
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Remove-CcCertificationAuthorityFile コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

