---
title: Skype for Business Server 2015 での集中ログ サービス構成設定の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '概要: Skype for Business Server 2015 の集中ログ サービスの構成設定を取得、更新、および作成する方法について説明します。'
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098863"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービス構成設定の管理

**概要:** Skype for Business Server 2015 の集中ログ サービスの構成設定を取得、更新、および作成する方法について説明します。

集中ログ サービスは、個別のコンピューターの集中ログ サービス エージェント (CLSAgent) にコマンドを送信するために、集中ログ サービス コントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。 エージェントは、送信されるコマンドを処理し(Start コマンドの場合)、シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従ってトレース ログの収集を開始します。

> [!IMPORTANT]
>  集中ログ Windows PowerShell一覧にあるすべてのコマンドレットが、Skype for Business Server 2015 のオンプレミス展開で使用することを目的としているのではありません。 動作するように見える場合でも、次のコマンドレットは Skype for Business Server 2015 オンプレミス展開では機能するようには設計されません。

-  **CsClsRegion** コマンドレット: [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) [、Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps) [、New-CsClsRegion、Remove-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)。 [](/powershell/module/skype/remove-csclsregion?view=skype-ps)
-  **CsClsSearchTerm コマンドレット:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) および [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup** コマンドレット: [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [、Set-CsClsSecurityGroup、New-CsClsSecurityGroup、](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)[および Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。 [](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)

これらのコマンドレットで定義されている設定は、悪影響を及ぼしたり、悪影響を及ぼしたりしませんが、Microsoft 365 または Office 365 で使用するように設計され、オンプレミス展開では予期した結果を得る必要はありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。

集中ログ サービスは、1 台のコンピューターまたはコンピューターのプールを含むスコープ (展開内のコンピューターとプールのコレクションを含むサイト Redmond などの定義されたサイト) またはグローバル スコープ (展開内のすべてのコンピューターとプール) で実行できます。

Skype for Business Server 管理シェルを使用して集中ログ サービス スコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループ、またはこれら 2 つのグループのいずれかを含むカスタム RBAC 役割のメンバーである必要があります。 このコマンドレットが割り当てられているすべての RBAC 役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> コマンド ライン コマンドと CLSController で実行できる基本的なWindows PowerShellがあります。 Windows PowerShellシナリオを構成および定義し、それらのシナリオをトラブルシューティング シナリオに対して有意義な方法で再利用するための豊富な方法を提供します。 CLSController はコマンドを発行して結果を得る迅速かつ効率的な方法を提供しますが、CLSController のコマンド セットは、コマンド ラインから使用できる有限のコマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController は新しいシナリオを定義したり、サイトまたはグローバル レベルでスコープを管理したり、動的に構成できない有限コマンド セットのその他の多くの制限を定義することはできません。 CLSController は高速実行のための手段を提供しますが、Windows PowerShell は CLSController で可能な機能を超えて集中ログ サービス機能を拡張する手段を提供します。

[Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps)、 Stop-CsClsLogging 、 [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps)および[](/powershell/module/skype/stop-csclslogging?view=skype-ps)[Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps)コマンドの実行中に、-Computers パラメーターを使用して単一のコンピューター スコープを定義できます。 -Computers パラメーターは、ターゲット コンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを受け入れる。

> [!TIP]
> ログ コマンドを実行する -Pools とコンマ区切りのプールの一覧を定義することもできます。

サイトスコープとグローバル スコープは **、New-、Set-、Remove-** の集中ログ サービスコマンドレットで定義されます。   次の例では、サイトとグローバル スコープを設定する方法を示します。

> [!IMPORTANT]
> 表示されるコマンドには、他のセクションで説明されているパラメーターと概念が含まれている場合があります。 この例のコマンドは、スコープを定義するために **-Identity** パラメーターを使用することを示す目的で使用され、その他のパラメーターは完全性とスコープを指定するために含まれています。 **Set-CsClsConfiguration** コマンドレットの詳細については、「操作」のドキュメントの [「Set-CsClsConfiguration」](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)を参照してください。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中ログ サービス構成を取得するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Get-CsClsConfiguration
   ```

**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。**Get-CsClsConfiguration** を実行すると、展開に現在既定のグローバル構成がありますが、サイト構成が定義されていない次のスクリーン ショットのような情報が表示されます。

![Get-CsClsConfiguration からの出力例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカル ストアから現在の集中ログ サービス構成を取得するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

**Get-CsClsConfiguration** でパラメーターを指定しない最初の例を使用すると、このコマンドはデータの中央管理ストアを参照します。 パラメーター -LocalStore を指定すると、サーバーの全体管理ストアではなく、コンピューターの LocalStore が参照されます。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のようにします。

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

コマンドレット **Get-CsClsConfiguration は** 、常に特定のスコープの構成の一部であるシナリオを表示します。 ほとんどの場合、すべてのシナリオが表示されないので、切り捨てられて表示されます。 ここで使用するコマンドは、すべてのシナリオと、使用するプロバイダー、設定、およびフラグに関する部分的な情報を一覧表示します。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>サーバーを使用して集中ログ サービスのグローバル スコープを更新Windows PowerShell

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

このコマンドは、展開内の各コンピューターとプールの CLSAgent に対して、トレース ファイルのロールオーバー値のサイズを 40 メガバイトに設定します。 すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレース ログのロールオーバー値を 40 メガバイトに設定します。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>サーバーを使用して集中ログ サービスのサイト スコープを更新するにはWindows PowerShell

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 例で説明した通り、ログ ファイルの既定の場所は %TEMP%\Tracing です。 ただし、ファイルを書き込むのは実際には CLSAgent であり、CSLAgent はネットワーク サービスとして実行されます。%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。

このコマンドは、サイト Redmond の各コンピューターとプールの CLSAgent に対して、トレース ファイルのロールオーバー値のサイズを 40 メガバイトに設定します。 他のサイトのコンピューターとプールはコマンドの影響を受け、既定で定義されている現在構成されているトレース ログロールオーバー値 (20 メガバイト) またはログ 記録セッションの開始時に引き続き使用されます。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい集中ログ サービス構成を作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration多数のオプション構成設定にアクセスできます。 構成オプションの詳細については [、「Get-CsClsConfiguration」](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) および「集中ログ サービス構成設定について [」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)。

たとえば、キャッシュ ファイルのネットワーク フォルダー、ログ ファイルのロールオーバー期間、ログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次の入力を行います。

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

新しい構成の作成と、集中ログ サービスの新しいプロパティの定義方法を慎重に計画する必要があります。 変更は慎重に行い、問題のシナリオを適切にログに記録する能力への影響を理解する必要があります。 ログをサイズとロールオーバー期間に管理する機能を強化し、問題が発生した場合に問題解決を可能にする構成を変更する必要があります。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の集中ログ サービス構成を削除するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. コマンド ライン プロンプトで次のコマンドを入力します。

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

たとえば、ログ ファイルのロールオーバー時間を増やして作成した集中ログ サービス構成を削除するには、ロールオーバー ログ ファイルのサイズを大きくし、ログ ファイルのキャッシュの場所を次のようにネットワーク共有に設定します。

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> これは、「新しい集中ログ サービス構成を作成するには」の手順で作成された新しい構成です。

サイト レベルの構成を削除する場合、サイトはグローバル設定を使用します。
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する](configure-providers.md)

[Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する](configure-scenarios.md)

[Skype for Business 2015 の集中ログ サービス](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)