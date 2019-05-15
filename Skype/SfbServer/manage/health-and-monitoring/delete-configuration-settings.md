---
title: CDR 構成設定の Skype ビジネス サーバーの既存のコレクションを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '概要: は、Skype のビジネス サーバーの CDR 構成設定を削除する方法を説明します。'
ms.openlocfilehash: 2319cd8548b3f183af6e54bbe1f24870093ae641
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926551"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>CDR 構成設定の Skype ビジネス サーバーの既存のコレクションを削除します。
 
**の概要:** Skype のビジネス サーバーの CDR 構成設定を削除する方法について説明します。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
ビジネス サーバー、1 つの Skype をインストールすると、CDR 構成設定のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープ設定を削除した場合、CDR はそのサイトでグローバル設定を使用して管理されます。
  
削除することも""グローバル設定に注意してください。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、既定では CDR 構成設定のコレクションで削除が有効になります。 削除が無効になるようにグローバル コレクションを変更すると想定します。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
CDR 構成設定を削除するには、Skype をビジネス サーバーのコントロール パネルの[削除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットを使用しています。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype で CDR 構成設定を削除するのには

1. ビジネス サーバーのコントロール パネルの Skype は、[**監視およびアーカイブ**をクリックします。 
    
2. [**通話詳細記録**] タブで、削除する CDR 設定のコレクションを 1 つまたは複数選択します。複数のコレクションを選択するには、最初のコレクションをクリックし、Ctrl キーを押しながら他のコレクションをクリックします。
    
3. [**編集**] をクリックして、[**削除**] をクリックします。
    
4. [Skype ビジネス サーバーのコントロール パネル] ダイアログ ボックスでは、 **[ok]** をクリックします。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、CDR 構成設定を削除します。

Windows PowerShell と**削除 CsCdrConfiguration**コマンドレットを使用して構成設定を記録する呼び出しの詳細を削除することができます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>指定された CDR 構成設定のコレクションを削除するには

 このコマンドでは、Redmond サイトに適用されていた CDR 構成設定が削除されます。
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されていた CDR 構成設定をすべて削除するには

 このコマンドでは、サイト スコープに適用されていたすべての CDR 構成設定が削除されます。
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>通話詳細記録を無効にする CDR 構成設定をすべて削除するには

 このコマンドでは、通話詳細記録が無効になっているすべての CDR 構成設定が削除されます。
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

詳細については、[削除 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[ビジネス サーバーの通話詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

