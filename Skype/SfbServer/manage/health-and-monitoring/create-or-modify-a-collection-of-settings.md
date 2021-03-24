---
title: Skype for Business Server で CDR 構成設定のコレクションを作成または変更する
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '概要: Skype for Business Server の通話詳細記録 (CDR) について説明します。'
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095371"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で CDR 構成設定のコレクションを作成または変更する
 
**概要:** Skype for Business Server の通話詳細記録 (CDR) について説明します。
  
通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
Skype for Business Server をインストールすると、CDR 構成設定のグローバル コレクションが 1 つ作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。 たとえば、レドモンド サイトにサイト スコープの設定を作成する場合、レドモンドでの CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。
  
Skype for Business Server コントロール パネルまたは [New-CsCdrConfiguration コマンドレットを使用して、CDR 構成設定を作成](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) できます。 Skype for Business Server コントロール パネルまたは [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットを使用して、既存の設定を変更できます。 Skype for Business Server コントロール パネルを使用して設定を作成または変更する場合は、次のオプションを使用できます。
  
|**UI 設定**|**PowerShell パラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |ID  <br/> |作成する CDR 構成設定に対する一意の識別子。これらの設定はサイト スコープでのみ作成できます。  <br/> |
|CDR の監視を有効にする  <br/> |EnableCDR  <br/> |CDR を有効にするかどうかを示します。  <br/> |
|CDR の削除を有効にする  <br/> |EnablePurging  <br/> |CDR の記録を CDR データベースから定期的に削除するかどうかを示します。  <br/> |
|Keep CDRs for maximum duration (days) (CDR の最大保持期間 (日))  <br/> |KeepCallDetailForDays  <br/> |CDR データベースに CDR レコードを保持する日数を示します。指定された日数より古いレコードは、自動的に削除されます (削除が実行されるのは、削除が有効になっている場合のみです)。  <br/> |
|エラー報告データを保持する最大期間 (日数)  <br/> |KeepErrorReportForDays  <br/> |CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、クライアント アプリケーションによってアップロードされる診断レポートです。  <br/> |
   
> [!NOTE]
> このNew-CsCdrConfigurationおよびSet-CsCdrConfigurationには、Skype for Business Server コントロール パネルで使用できない追加のオプションが含まれます。 詳細については [、「New-CsCdrConfiguration」](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) および [「Set-CsCdrConfiguration」](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) のヘルプ トピックを参照してください。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して CDR 構成設定を作成するには

1. [Skype for Business Server コントロール パネル] で、[監視 **とアーカイブ] をクリックします**。
    
2. [通話の詳細 **記録] タブで** 、[新規] を **クリックします**。
    
3. [**サイトの選択**] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。
    
4. [**新しい通話詳細記録 (CDR) 設定を作成する**] ダイアログで、任意に選択を行ってから [**コミット**] をクリックします。
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して既存の CDR 構成設定を変更するには

1. [Skype for Business Server コントロール パネル] で、[監視 **とアーカイブ] をクリックします**。
    
2. 変更する設定のコレクションをダブルクリックするか、コレクションを選択して [**編集**] をクリックし、さらに [**詳細の表示**] をクリックします。 一度に変更できるのは 1 つのコレクションだけであることに注意してください。 複数のコレクションに同じ変更を加える場合は、代わりに Skype for Business Server 管理シェルを使用します。
    
3. [**編集 通話詳細記録 (CDR) 設定**] ダイアログで、任意の選択を行ってから [**コミット**] をクリックします。
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 構成Windows PowerShell作成する

CDR 構成設定を作成するには、このコマンドレットと **New-CsCdrConfiguration** コマンドレットWindows PowerShellを使用して作成することもできます。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションを作成するには

 このコマンドを実行すると、レドモンド サイトに適用される新しい CDR 構成設定のコレクションが作成されます。
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには

 前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには

 複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

詳細については [、New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
