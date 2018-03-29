---
title: 発行 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a>発行 CcAppliance
 
Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、オンラインのテナント構成の高可用性の情報を取得し、クラウド コネクタ アプライアンス ホスト サーバー上に公開します。
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

高可用性の情報には、PSTN サイトの仲介サーバーの FQDN と IP アドレスが含まれます。新しい DNS A レコードが、仲介サーバーの IP アドレスの AD サーバーに追加されます。新しいトポロジ項目が、仲介サーバーの FQDN と IP アドレスの中央管理ストアに更新されます。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Publish-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[インストール CcAppliance](install-ccappliance.md)
  
[アンインストール CcAppliance](uninstall-ccappliance.md)
  
[登録 CcAppliance](register-ccappliance.md)
  
[登録解除 CcAppliance](unregister-ccappliance.md)
  

