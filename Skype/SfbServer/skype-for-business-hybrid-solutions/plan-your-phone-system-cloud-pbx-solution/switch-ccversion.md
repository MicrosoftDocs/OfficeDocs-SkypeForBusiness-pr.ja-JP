---
title: スイッチ CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Switch-CcVersion コマンドレットは、実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a>スイッチ CcVersion
 
Switch-CcVersion コマンドレットは、実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、現在実行中のアプライアンスのサービスをドレインして、新規に展開されたアプライアンスまたはバックアップ アプライアンスに切り替えます。
  
```
Switch-CcVersion
```

### <a name="example-2"></a>例 2

次の例では、現在実行中のアプライアンスのサービスをドレインし、サービスのドレインに失敗した場合は強制的にサービスを停止します。 コマンドにより、新規に展開されたアプライアンスまたはバックアップ アプライアンスへの接続が切断されます。
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

スイッチ CcVersion コマンドレットでは、仲介サーバーとエッジ サーバーのコネクタのクラウド サービスがドレインされます。 すべての実行中の通話は終了しますが、新しい通話はアプライアンスによって拒否されます。 ドレイン後、コマンドレットにより企業ネットワークおよびインターネット ネットワークから実行中のアプライアンスが切断され、アプライアンスに属しているすべての仮想マシンがオフになり、企業ネットワークおよびインターネット ネットワークにバックアップ アプライアンスが接続されます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 省略可能 <br/> |System.Management.Automation.SwitchParameter  <br/> | サービスのドレインに失敗した場合は強制的にサービスを停止します。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

