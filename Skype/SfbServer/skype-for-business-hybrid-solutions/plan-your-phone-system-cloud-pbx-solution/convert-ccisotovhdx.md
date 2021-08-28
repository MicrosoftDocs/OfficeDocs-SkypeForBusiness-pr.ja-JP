---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: このConvert-CcIsoToVhdxは、R2 ISO ファイルで提供された顧客を使用して、基本仮想ハード ディスク ファイル (VHDX) Windows Server 2012作成します。 VHDX ファイルは、仮想マシンの展開中にSkype for Business クラウド コネクタ エディション。
ms.openlocfilehash: dcbe1b4939fd99d6200217925bc52b72f6868873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635071"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
このConvert-CcIsoToVhdxは、R2 ISO ファイルで提供された顧客を使用して、基本仮想ハード ディスク ファイル (VHDX) Windows Server 2012作成します。 VHDX ファイルは、仮想マシンの展開中にSkype for Business クラウド コネクタ エディション。
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>パラメーター

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必須 <br/> |System.String  <br/> | R2 ISO ファイルWindows Server 2012パス。 <br/> |
|GeneralizeOnly  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |更新中に変換プロセスがWindows場合は、ネットワーク/プロキシを構成し、手動でWindowsできます。 手動作業が完了したら、-GeneralizeOnly パラメーターを使用してこのコマンドレットを実行すると、残りのジョブが完了します。  <br/> |
|PauseBeforeUpdate  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |データベースを更新Windows、基本 VM 上の手動ネットワーク/プロキシ構成が必要になる場合があります。 このパラメーターが指定されている場合、Windowsが更新される前に、変換プロセスが一時停止します。 手動構成が完了したら、プロセスを再開できます。  <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、"C:\Windows_Server_2012_R2-EN-US-x64.ISO" にある Windows Server 2012 R2 ISO ファイルを使用してベース VHDX ファイルを準備します。 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>例 2

更新中Convert-CcIsoToVhdxコマンドレットがWindows場合、ネットワーク/プロキシの構成が正しくない可能性があります。 エラー メッセージの指示に従って、基本仮想マシンにログオンして問題を解決し、手動でWindowsできます。 手動作業が完了したら、-GeneralizeOnly パラメーターを使用してコマンドレットを再度実行して、残りのジョブを完了します。 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>例 3

データを更新するために手動構成が必要Windows-PauseBeforeUpdate パラメーターを使用できます。 このパラメーターを使用すると、クラウド コネクタは更新プロセスの前Windows一時停止します。 次に、手動構成を完了し、次のように変換プロセスを再開できます。
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このConvert-CcIsoToVhdxは、最初に基本 VM を作成し、Cloud Connector が依存する基本的なコンポーネントをインストールし、次に更新プログラムWindowsします。 最後に、仮想マシン (sysprep) を一般化して、クラウド コネクタ アプライアンスの仮想マシンで使用されるベース VHDX ファイルを取得します。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このConvert-CcIsoToVhdxは、パイプライン処理された入力を受け付け取らない。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

