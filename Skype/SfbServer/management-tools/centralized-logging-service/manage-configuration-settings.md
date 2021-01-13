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
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835157"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービス構成設定の管理

**概要:** Skype for Business Server 2015 の集中ログ サービスの構成設定を取得、更新、および作成する方法について説明します。

集中ログ サービスは、個別のコンピューターの集中ログ サービス エージェント (CLSAgent) にコマンドを送信するために、集中ログ サービス コントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。 エージェントは送信されたコマンドを処理し、(Start コマンドの場合) シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従ってトレース ログの収集を開始します。

> [!IMPORTANT]
>  集中ログ Windows PowerShell一覧に記載されているコマンドレットの中には、Skype for Business Server 2015 のオンプレミス展開での使用を目的としていないものがあります。 機能するように見える場合でも、次のコマンドレットは Skype for Business Server 2015 のオンプレミス展開で機能するようには設計されません。

-  **CsClsRegion コマンドレット:** Get-CsClsRegion、Set-CsClsRegion、New-CsClsRegion、Remove-CsClsRegion 。 [](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)
-  **CsClsSearchTerm コマンドレット:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) および [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup コマンドレット:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [、Set-CsClsSecurityGroup、New-CsClsSecurityGroup、](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)[および Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。 [](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)

これらのコマンドレットで定義されている設定は、動作を妨げたり、悪影響を引き起こしたりしませんが、Microsoft 365 または Office 365 で使用するように設計され、オンプレミス展開で予期される結果が得られる可能性はありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。

集中ログ サービスは、1 台のコンピューターまたはコンピューターのプールを含むスコープ、サイト スコープ (つまり、展開内のコンピューターとプールのコレクションを含むサイト Redmond などの定義済みサイト)、またはグローバル スコープ (展開内のすべてのコンピューターとプール) で実行できます。

Skype for Business Server 管理シェルを使用して集中ログ サービススコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーか、これら 2 つのグループのいずれかを含むカスタム RBAC の役割のメンバーである必要があります。 このコマンドレットが割り当てられているすべての RBAC の役割 (自身が作成したカスタムの RBAC の役割を含む) の一覧を戻す場合は、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> コマンド ライン コマンドと CLSController の間には、基本的なWindows PowerShellがあります。 Windows PowerShellは、シナリオを構成および定義し、それらのシナリオをトラブルシューティング シナリオに役立つ方法で再利用するための豊富な方法を提供します。 CLSController は、コマンドを発行して結果を取得するための高速かつ効率的な方法を提供しますが、CLSController のコマンド セットは、コマンド ラインから使用できる限られたコマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController は新しいシナリオの定義、サイト レベルまたはグローバル レベルでの範囲の管理、および動的に構成できない有限コマンド セットのその他の多くの制限を定義できません。 CLSController は高速実行の手段を提供しますが、Windows PowerShell は CLSController で可能な機能を超えて集中ログ サービスの機能を拡張する手段を提供します。

-Computers パラメーターを使用して、Search-CsClsLogging、Show-CsClsLogging、Start-CsClsLogging、Stop-CsClsLogging、Sync-CsClsLogging、Update-CsClsLogging コマンドの実行中に 1 つのコンピューター スコープを定義できます。 [](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) -Computers パラメーターには、対象のコンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを指定できます。

> [!TIP]
> また、-Pools と、ログ コマンドを実行するプールのコンマ区切りリストを定義することもできます。

サイトスコープとグローバル スコープは **、New-、Set-、****および** **Remove-** の集中ログ サービスコマンドレットで定義されます。 次の例は、サイトとグローバル スコープを設定する方法を示しています。

> [!IMPORTANT]
> 表示されるコマンドには、他のセクションで説明されているパラメーターと概念が含まれている場合があります。 このサンプル コマンドは **、-Identity** パラメーターを使用して範囲を定義する方法を示し、その他のパラメーターは完全に機能し、スコープを指定するために含まれています。 **Set-CsClsConfiguration** コマンドレットの詳細については、「操作」のドキュメントの [「Set-CsClsConfiguration」](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)を参照してください。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中ログ サービス構成を取得するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Get-CsClsConfiguration
   ```

**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。**Get-CsClsConfiguration** を実行すると、次のスクリーン ショットのような情報が表示されます。このスクリーン ショットでは、展開には既定のグローバル構成がありますが、サイト構成は定義されていません。

![Get-CsClsConfiguration からの出力例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカル ストアから現在の集中ログ サービス構成を取得するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

**Get-CsClsConfiguration** でパラメーターが指定されていない最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。 パラメーター -LocalStore を指定すると、コマンドは中央管理ストアではなく、コンピューター LocalStore を参照します。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のようにします。

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

**Get-CsClsConfiguration** コマンドレットは、特定のスコープの構成の一部であるシナリオを常に表示します。 ほとんどの場合、すべてのシナリオが表示されないので、切り詰められて表示されます。 ここで使用するコマンドは、すべてのシナリオと、使用されているプロバイダー、設定、フラグに関する部分的な情報を一覧表示します。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>次のコマンドを使用して集中ログ サービスのグローバル スコープを更新Windows PowerShell

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

このコマンドは、展開内の各コンピューターおよびプールの CLSAgent に対して、トレース ファイルのロールオーバー値のサイズを 40 MB に設定します。 すべてのサイトのコンピューターとプールは、このコマンドの影響を受け、構成済みのトレース ログのロールオーバー値を 40 MB に設定します。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>管理ログ サービスを使用して集中ログ サービスのサイト スコープを更新Windows PowerShell

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 例で説明したログ ファイルの既定の場所は %TEMP%\Tracing です。 ただし、ファイルを書き込むのは実際には CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるので、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。

このコマンドは、トレース ファイルのロールオーバー値のサイズを 40 MB に設定するために、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。 他のサイトのコンピューターとプールはコマンドの影響を受け、既定 (20 MB) またはログ セッションの開始時に定義されている現在構成されているトレース ログのロールオーバー値を引き続き使用します。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい集中ログ サービス構成を作成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfigurationは、多数のオプション構成設定にアクセスできます。 構成オプションの詳細については [、「Get-CsClsConfiguration」](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) および [「Understanding Centralized Logging Service Configuration Settings」を参照してください](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。

たとえば、キャッシュ ファイルのネットワーク フォルダー、ログ ファイルのロールオーバー期間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のコマンドを入力します。

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

新しい構成の作成と、集中ログ サービスの新しいプロパティの定義方法を慎重に計画する必要があります。 変更は慎重に行い、問題のシナリオを適切にログに記録する機能への影響を理解する必要があります。 ログを管理する機能を拡張する構成に変更を加え、問題が発生した場合に問題を解決できるロールオーバー期間を設定する必要があります。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の集中ログ サービス構成を削除するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

2. コマンド ライン プロンプトで次を入力します。

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

たとえば、ログ ファイルのロールオーバー時間を増加するために作成した集中ログ サービス構成を削除するには、ロールオーバー ログ ファイルのサイズを増やし、ログ ファイルのキャッシュの場所をネットワーク共有に次のように設定します。

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> これは、「新しい集中ログ サービス構成を作成するには」の手順で作成した新しい構成です。

サイト レベルの構成を削除する場合、サイトはグローバル設定を使用します。
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での集中ログ サービスのプロバイダーの構成](configure-providers.md)

[Skype for Business Server 2015 の集中ログ サービスのシナリオを構成する](configure-scenarios.md)

[Skype for Business 2015 の集中ログ サービス](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
