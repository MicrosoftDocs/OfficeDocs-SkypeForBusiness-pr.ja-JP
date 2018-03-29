---
title: Skype for Business Server 2015 での CDR 構成情報の表示
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: ビジネス サーバー 2015 の Skype での呼び出しの詳細記録 (CDR) を使用する方法を説明します。'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での CDR 構成情報の表示
 
**の概要:**ビジネス サーバー 2015 の Skype での呼び出しの詳細記録 (CDR) を使用する方法について説明します。
  
通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
ビジネス サーバー 2015 年、1 つの Skype をインストールすると CDR 構成設定のグローバル コレクションが作成されます。 管理者は、個別のサイトに適用できるカスタム設定コレクションを作成することもできます。 Skype ビジネス サーバーのコントロール パネルまたは[Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットを使用して、使用中で、組織で CDR 構成設定を表示できます。
  
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
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

詳細については、 [Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

