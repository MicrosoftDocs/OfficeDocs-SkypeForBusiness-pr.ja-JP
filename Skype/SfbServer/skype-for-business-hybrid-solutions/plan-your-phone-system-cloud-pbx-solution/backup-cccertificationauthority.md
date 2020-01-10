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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003027"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

証明機関のバックアップは、障害が発生した場合に備えて、同じ証明書を使ってクラウドコネクタのアプライアンスを再展開する場合や、新しいハードウェアにアプライアンスを移行する場合に便利です。 このコマンドは、クラウドコネクタ証明機関サービスのコピーを AD サーバーから "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12" に保存します。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Backup-CcCertificationAuthority コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

