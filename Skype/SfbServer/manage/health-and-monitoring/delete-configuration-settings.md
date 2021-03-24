---
title: Skype for Business Server の CDR 構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '概要: Skype for Business Server で CDR 構成設定を削除する方法について説明します。'
ms.openlocfilehash: 3ac961df352f26891ece9c69b7d62b37c4c015d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095311"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server の CDR 構成設定の既存のコレクションを削除する
 
**概要:** Skype for Business Server で CDR 構成設定を削除する方法について説明します。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
Skype for Business Server をインストールすると、CDR 構成設定の単一のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。
  
グローバル設定を "削除" することもできます。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、既定では CDR 構成設定のコレクションでパージが有効になります。 パージが無効になるようにグローバル コレクションを変更すると想定します。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
SKYPE for Business Server コントロール パネルまたは [Remove-CsCdrConfiguration コマンドレットを使用して、CDR 構成設定を削除](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) できます。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して CDR 構成設定を削除するには

1. Skype for Business Server コントロール パネルで、[監視とアーカイブ **] をクリックします**。 
    
2. [**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。
    
3. [**編集**] をクリックして、[**削除**] をクリックします。
    
4. [Skype for Business Server コントロール パネル] ダイアログ ボックスで **、[OK] をクリックします**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 構成設定Windows PowerShellする

通話詳細記録構成設定を削除するには、Windows PowerShell **Remove-CsCdrConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>指定された CDR 構成設定のコレクションを削除するには

 このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されている CDR 構成設定をすべて削除するには

 このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

詳細については [、Remove-CsCdrConfiguration コマンドレットのヘルプ トピックを参照](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server の通話詳細記録データベースと Quality of Experience データベースを手動で削除する](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)