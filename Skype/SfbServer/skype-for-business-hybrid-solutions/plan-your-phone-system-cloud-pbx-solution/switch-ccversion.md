---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: このSwitch-CcVersionコマンドレットは、実行中のアプライアンスを切断し、新しく展開されたアプライアンスまたはバックアップ アプライアンスに切り替します。
ms.openlocfilehash: 9b15310956f80a9269c8fb611a0f7c6c06f561e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580331"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
このSwitch-CcVersionコマンドレットは、実行中のアプライアンスを切断し、新しく展開されたアプライアンスまたはバックアップ アプライアンスに切り替します。 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、現在実行中のアプライアンスのサービスをドレインし、新しく展開またはバックアップ するアプライアンスに切り替えました。
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>例 2

次の例では、現在実行中のアプライアンスのサービスをドレインし、サービスのドレインが失敗した場合にサービスを強制的に停止します。 次に、新しく展開されたアプライアンスまたはバックアップ アプライアンスに切り替え、次のコマンドを実行します。
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このSwitch-CcVersionコマンドレットは、仲介サーバーとエッジ サーバー上のクラウド コネクタ サービスをドレインします。 実行中のすべての呼び出しは完了しますが、アプライアンスは新しい通話を拒否します。 ドレイン後、コマンドレットは実行中のアプライアンスを企業ネットワークとインターネット ネットワークから切断し、アプライアンスに属するすべての仮想マシンをオフにしてから、バックアップ アプライアンスを企業ネットワークとインターネット ネットワークに接続します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 省略可 <br/> |System.Management.Automation.SwitchParameter  <br/> | サービスのドレインが失敗した場合、サービスを強制的に停止します。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

