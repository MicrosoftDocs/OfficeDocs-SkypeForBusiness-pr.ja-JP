---
title: Skype for Business Server で CDR 構成情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: Skype for Business Server で通話の詳細記録 (CDR) を使用する方法について説明します。'
ms.openlocfilehash: 976f61ac98cb02a0cd69750a581bfa5190156ff7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991682"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Skype for Business Server で CDR 構成情報を表示する
 
**概要:** Skype for Business Server で通話の詳細記録 (CDR) を使用する方法について説明します。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
Skype for Business Server をインストールすると、1つのグローバルな CDR 構成設定が作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 Skype for Business Server コントロールパネルまたは[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットを使用して、組織内で使用されている CDR 構成設定を表示できます。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して CDR 構成情報を表示するには

1. Skype for Business Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。
    
2. すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した CDR 構成情報の表示

CDR 構成設定は、Windows PowerShell と CsCdrConfiguration コマンドレットを使用して表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-view-cdr-configuration-information"></a>CDR の構成情報を表示するには

- すべての CDR 構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
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

詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  

