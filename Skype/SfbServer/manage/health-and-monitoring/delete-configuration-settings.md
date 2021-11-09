---
title: サーバー内の CDR 構成設定の既存のコレクションを削除Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '概要: CDR 構成設定を削除する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 8218d0b51045d3962825555bd5b248cb58262a37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854321"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>サーバー内の CDR 構成設定の既存のコレクションを削除Skype for Business Server
 
**概要:** このページで CDR 構成設定を削除するSkype for Business Server。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
サーバーをインストールSkype for Business Server、CDR 構成設定の単一のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。
  
グローバル設定を "削除" することもできます。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、既定では CDR 構成設定のコレクションでパージが有効になります。 パージが無効になるようにグローバル コレクションを変更すると想定します。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
CDR 構成設定を削除するには、Skype for Business Serverまたは[Remove-CsCdrConfiguration コマンドレットを使用](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)します。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して CDR 構成Skype for Business Server削除するには

1. [コントロール Skype for Business Server] で、[監視と **アーカイブ] をクリックします**。 
    
2. [**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。
    
3. [**編集**] をクリックして、[**削除**] をクリックします。
    
4. [コントロール Skype for Business Server] ダイアログ ボックスで **、[OK] をクリックします**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 構成設定Windows PowerShellする

通話詳細記録構成設定を削除するには、Windows PowerShell **Remove-CsCdrConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
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

[通話の詳細記録と Quality of Experience データベースを手動で削除Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)