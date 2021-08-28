---
title: CDR の構成情報を表示するSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: 通話詳細記録 (CDR) を使用する方法については、Skype for Business Server。'
ms.openlocfilehash: 8bd8ef54510a7353d39735b587d1e1a2a1373fe3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586909"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>CDR の構成情報を表示するSkype for Business Server
 
**概要:** 通話詳細記録 (CDR) を使用する方法については、Skype for Business Server。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
サーバーをインストールSkype for Business Server、CDR 構成設定の単一のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 組織で使用されている CDR 構成設定を表示するには、Skype for Business Server[または Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットを使用します。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して CDR 構成情報Skype for Business Serverするには

1. [コントロール Skype for Business Server] で、[監視 **とアーカイブ] をクリックします**。
    
2. すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 構成情報Windows PowerShell表示する

CDR 構成設定を表示するには、Windows PowerShellコマンドレットをGet-CsCdrConfigurationします。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した[Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-view-cdr-configuration-information"></a>CDR の構成情報を表示するには

- すべての CDR 構成設定に関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    次のような情報が表示されます。
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

詳細については [、Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
