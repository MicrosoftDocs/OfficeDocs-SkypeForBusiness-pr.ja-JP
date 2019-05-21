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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert-CcIsoToVhdx コマンドレットは、顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク　ファイル (VHDX) を作成します。VHDX ファイルは、Skype for Business Cloud Connector エディションの展開時に使用されます。
ms.openlocfilehash: 7b1426fe3180576e28780aeae96ee8e4913bb399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287539"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Convert-CcIsoToVhdx コマンドレットは、顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク　ファイル (VHDX) を作成します。VHDX ファイルは、Skype for Business Cloud Connector エディションの展開時に使用されます。
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>パラメーター

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必須 <br/> |System.String  <br/> | Windows Server 2012 R2 ISO ファイルのパス。 <br/> |
|GeneralizeOnly  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows の更新中に変換処理が失敗する場合は、ネットワーク/プロキシの構成を行い、手動で Windows を更新することができます。手動による作業が完了したら、-GeneralizeOnly　パラメーターを指定したコマンドレットを実行して残りのジョブを完了することができます。  <br/> |
|PauseBeforeUpdate  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows を更新するために、ベース VM で手動によるネットワーク/プロキシの構成が必要になる場合があります。このパラメーターが指定されている場合、Windows の更新前に変換プロセスは一時停止します。手動による構成を完了した後に、プロセスを再開できます。  <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、「C:\Windows_Server_2012_R2-EN-US-x64.ISO」に配置されている Windows Server 2012 R2 ISO ファイルを使用して、ベース VHDX ファイルを用意します。 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>例 2

Windows update の実行時に、変換によって CcIsoToVhdx コマンドレットが失敗した場合は、ネットワーク/プロキシの構成が正しくないことが原因として考えられます。 エラー メッセージ内の指示に従って、ベース仮想マシンにログ オンしてこの問題を修正し、手動で Windows を更新することができます。 手動による作業が完了したら、-GeneralizeOnly パラメーターを指定したコマンドレットを再び実行して、残りのジョブを完了します。 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>例 3

Windows を更新するのに手動による構成が必要な場合、-PauseBeforeUpdate パラメーターを使用できます。 このパラメーターを指定すると、Windows update プロセスの前にクラウドコネクタが一時停止します。 その後、手動による構成を完了して、次のように変換処理を再開できます。
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

-CcIsoToVhdx コマンドレットは、最初にベース VM を作成し、クラウドコネクタが依存する基本的なコンポーネントをインストールしてから、Windows の更新プログラムをインストールします。 最後に、仮想マシン (sysprep) を generalizes して、クラウドコネクタアプライアンスの仮想マシンで使用される基本 VHDX ファイルを取得します。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Convert-CcIsoToVhdx　コマンドレットはパイプライン入力を受け入れません。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

