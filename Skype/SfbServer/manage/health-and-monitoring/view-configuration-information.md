---
title: ビジネス サーバーの Skype でのビューの CDR 構成の情報
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: は、Skype のビジネス サーバーの呼び出しの詳細記録 (CDR) を使用する方法を説明します。'
ms.openlocfilehash: 5efa27942f91888218ddb1725ffe491fa6992776
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898060"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのビューの CDR 構成の情報
 
**の概要:** Skype のビジネス サーバーの呼び出しの詳細記録 (CDR) を使用する方法について説明します。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
ビジネス サーバー、1 つの Skype をインストールすると、CDR 構成設定のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 Skype ビジネス サーバーのコントロール パネルまたは[Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットを使用して、使用中で、組織で CDR 構成設定を表示できます。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、CDR 構成情報を表示するのには

1. Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。
    
2. すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、CDR 構成情報を表示します。

CDR 構成設定を表示するには、Windows PowerShell と Get CsCdrConfiguration コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-view-cdr-configuration-information"></a>CDR の構成情報を表示するには

- すべての CDR 構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。
    
  ```
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

詳細については、 [Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

