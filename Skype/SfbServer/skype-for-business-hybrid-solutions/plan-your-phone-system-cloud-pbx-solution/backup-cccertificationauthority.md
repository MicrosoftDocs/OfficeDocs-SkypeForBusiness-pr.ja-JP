---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234552"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

同じ証明書、障害発生時にクラウドのコネクタのアプライアンスを再展開する場合、またはアプライアンスを新しいハードウェアに移動する場合は、証明機関のバックアップは役に立ちます。 コマンドに AD サーバーからクラウド コネクタ証明機関サービスのコピーを保存する"\<SiteRootDirectory\>\CA\SfB CCE Root.p12」です。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Backup-CcCertificationAuthority コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

