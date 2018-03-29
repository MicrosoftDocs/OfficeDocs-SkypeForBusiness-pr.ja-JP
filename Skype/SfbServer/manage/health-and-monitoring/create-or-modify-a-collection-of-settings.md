---
title: Skype for Business Server 2015 での CDR 構成設定のコレクションの作成または変更
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '概要: は、Skype でのビジネス サーバー 2015 (CDR) を記録呼び出しの詳細について説明します。'
ms.openlocfilehash: 9861c3e2fba0f601e47e093a664999052d128f95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での CDR 構成設定のコレクションの作成または変更
 
**の概要:**ビジネス サーバー 2015 の Skype で (CDR) の記録の呼び出しの詳細について説明します。
  
通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。
  
ビジネス サーバー 2015 1 つの Skype をインストールすると、CDR 構成設定のグローバル コレクションが作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。 たとえば、Redmond サイトにサイト スコープの設定を作成する場合、Redmond での CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。
  
ビジネス サーバーのコントロール パネルまたは[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)コマンドレットのいずれかの Skype を使用して、CDR 構成設定を作成できます。 Skype ビジネス サーバーのコントロール パネルの[設定 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用するには既存の設定を変更します。 作成または設定を変更するビジネス サーバーのコントロール パネルの Skype を使用する場合に使用可能な次のオプションになります。
  
|**UI の設定**|**PowerShell のパラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |ID  <br/> |作成する CDR 構成設定に対する一意の識別子。これらの設定はサイト スコープでのみ作成できます。  <br/> |
|CDR の監視を有効にする  <br/> |EnableCDR  <br/> |CDR が有効かどうかを示します。  <br/> |
|CDR の削除を有効にする  <br/> |EnablePurging  <br/> |CDR の記録を CDR データベースから定期的に削除するかどうかを示します。  <br/> |
|CDR を保持する最大期間 (日数)  <br/> |KeepCallDetailForDays  <br/> |CDR データベースに CDR レコードを保持する日数を示します。指定された日数より前のレコードは、自動的に削除されます (削除が実行されるのは、削除が有効になっている場合のみです)。  <br/> |
|エラー報告データを保持する最大期間 (日数)  <br/> |KeepErrorReportForDays  <br/> |CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、クライアント アプリケーションによってアップロードされる診断レポートです。  <br/> |
   
> [!NOTE]
> 新規 CsCdrConfiguration とセット CsCdrConfiguration コマンドレットには、ビジネス サーバーのコントロール パネルの Skype では利用できない追加のオプションが含まれています。 [新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)と、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)ヘルプ トピックの詳細についてを参照してください。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、CDR 構成設定を作成するには

1. Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。
    
2. **呼び出しの詳細記録**] タブで、[**新規**を] をクリックします。
    
3. [**サイトの選択**] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。
    
4. [**新しい通話詳細記録 (CDR) 設定を作成する**] ダイアログで、任意に選択を行ってから [**コミット**] をクリックします。
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して既存の CDR 構成設定を変更するのには

1. Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。
    
2. 変更する設定のコレクションをダブルクリックするか、コレクションを選択して [**編集**] をクリックし、さらに [**詳細の表示**] をクリックします。 一度に変更できるのは 1 つのコレクションだけであることに注意してください。 同じ変更を複数のコレクションに加えると、代わりにビジネス サーバー管理シェルには、Skype を使用します。
    
3. [**通話詳細記録 (CDR) 設定の編集**] ダイアログで、任意の選択を行ってから [**コミット**] をクリックします。
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、CDR 構成設定を作成します。

CDR 構成の設定は、Windows PowerShell と**新規 CsCdrConfiguration**コマンドレットを使用して作成することもを作成することができます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションを作成するには

 このコマンドを実行すると、Redmond サイトに適用される新しい CDR 構成設定のコレクションが作成されます。
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには

 前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには

 複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

詳細については、[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

