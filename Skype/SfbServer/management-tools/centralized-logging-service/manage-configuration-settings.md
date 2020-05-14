---
title: Skype for Business Server 2015 での集中ログサービスの構成設定の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 2015 で集中ログサービスの構成設定を取得、更新、および作成する方法について説明します。'
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221177"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログサービスの構成設定の管理

**概要:** Skype for Business Server 2015 で集中ログサービスの構成設定を取得、更新、および作成する方法について説明します。

集中ログサービスは、個々のコンピューターの集中ログサービスエージェント (CLSController) にコマンドを送信するために、集中ログサービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。 エージェントは、エージェントに送信されたコマンドを処理し (開始コマンドの場合)、シナリオ、プロバイダ、トレース期間、フラグの構成を使用して、提供された構成情報に従ってトレースログの収集を開始します。

> [!IMPORTANT]
>  集中ログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Skype for Business Server 2015 社内展開で使用することを目的としたものではありません。 次のコマンドレットは、機能しているように見えても、Skype for Business Server 2015 の社内展開で機能するようには設計されていません。

-  **Csclsregion コマンドレット:** [取得-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)、および[Remove-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm コマンドレット:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) および [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **New-csclssecuritygroup コマンドレット:** [new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、および[Remove-new-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

これらのコマンドレットで定義されている設定は、悪影響を及ぼすことはありませんが、Microsoft 365 または Office 365 で使用するように設計されており、オンプレミスの展開で予期した結果をもたらすことはありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。

集中ログサービスは、1台のコンピューターまたはコンピューターのプール、サイトスコープ (展開内のコンピューターとプールのコレクションが含まれているサイト Redmond などの定義済みサイト)、またはグローバルスコープ (展開内のすべてのコンピューターとプール) に対して実行できます。

Skype for Business Server 管理シェルを使用して集中ログサービススコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。 このコマンドレットが割り当てられているすべての RBAC の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

次に例を示します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。 Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、これらのシナリオをトラブルシューティングのシナリオに合わせてわかりやすく再利用できます。 CLSController では、コマンドを発行して結果を取得する高速で効率的な方法が提供されていますが、CLSController のコマンドセットは、コマンドラインから使用可能な有限コマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController では新しいシナリオを定義したり、サイトまたはグローバルレベルでスコープを管理したり、動的に構成することができない制限されたコマンドセットに関するその他の多くの制限を設けたりすることはできません。 CLSController は高速実行の手段を提供しますが、Windows PowerShell では、集中化されたログサービス機能を、CLSController で可能な範囲を超えて拡張する手段が提供されています。

[検索-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) 、および-Computers パラメーターを使用した[更新-](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) csclslogging コマンドの実行中に、単一のコンピュータースコープを定義できます。 -Computers パラメーターには、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) をコンマで区切った一覧を指定します。

> [!TIP]
> また、ログコマンドを実行するプールとコンマで区切られた一覧を定義することもできます。

サイトとグローバルスコープは、**新しい-**、 **Set-** および**Remove-** 集中ログサービスのコマンドレットで定義されています。 次の例は、サイトとグローバルスコープを設定する方法を示しています。

> [!IMPORTANT]
> 表示されているコマンドには、他のセクションで説明しているパラメーターと概念が含まれている場合があります。 この例では、 **-Identity**パラメーターを使用してスコープを定義することを示し、他のパラメーターは完全に、そのスコープを指定することを目的としています。 **設定-csclsconfiguration**コマンドレットの詳細については、「操作」のドキュメントの「 [Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 」を参照してください。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中ログサービスの構成を取得するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration
   ```

新しい構成を作成したり、既存の構成を更新したりするには、**新しい-csclsconfiguration**および**Set-csclsconfiguration**コマンドレットを使用します。**取得-CsClsConfiguration**を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、展開には既定のグローバル構成がありますが、サイト構成は定義されていません。

![Get-CsClsConfiguration からの出力例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカルストアから現在の集中ログサービスの構成を取得するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

**Get-CsClsConfiguration**でパラメーターが指定されていない最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。 パラメーター-LocalStore を指定すると、コマンドは中央管理ストアの代わりにコンピューターの LocalStore を参照します。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    たとえば、グローバルスコープで定義されているシナリオを取得するには、次のようにします。

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

コマンドレットを**取得**すると、指定したスコープの構成の一部であるシナリオが常に表示されます。 ほとんどの場合、すべてのシナリオは表示されず、切り捨てられます。 ここで使用しているコマンドは、すべてのシナリオと、プロバイダー、設定、およびフラグを使用することに関する情報の一部を示しています。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログサービスのグローバルスコープを更新するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

このコマンドは、展開内の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定するように指示します。 すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレースログのロールオーバー値は40メガバイトに設定されます。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログサービスのサイトスコープを更新するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 例に示されているように、ログファイルの既定の場所は%TEMP%\Tracing. です。 ただし、実際には、ファイルを書き込み中で、CSLAgent はネットワークサービスとして実行されるので、このような場合、%Windir%\serviceprofiles\networkservice\appdata\local には% TEMP% 変数が展開されます。

このコマンドは、サイト Redmond の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定します。 他のサイト内のコンピューターとプールはコマンドの影響を受けず、現在構成されているトレースログのロールオーバー値 (既定値 (20 mb) またはログセッションの開始時) を引き続き使用します。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい集中ログサービスの構成を作成するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > 新しい-CsClsConfiguration を使用すると、多数のオプションの構成設定にアクセスできます。 構成オプションの詳細については、「[取得-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 」と「[集中ログサービスの構成設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)について」を参照してください。

たとえば、キャッシュファイル用のネットワークフォルダー、ログファイルのロールオーバー期間、およびログファイルのロールオーバーサイズを定義する新しい構成を作成するには、次のように入力します。

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

新しい構成の作成を慎重に計画し、集中ログサービスの新しいプロパティを定義する方法を検討する必要があります。 変更を行って、問題のシナリオを適切にログに記録する機能への影響を理解しておく必要があります。 ログの管理能力を向上させるように構成を変更する必要があります。これにより、問題が発生したときに問題を解決するためのサイズとロールオーバー期間が向上します。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の集中ログサービスの構成を削除するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。

2. コマンドラインプロンプトで次のように入力します。

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

たとえば、ログファイルのロールオーバー時間を長くするために作成した集中ログサービスの構成を削除するには、次のように、ロールオーバーログファイルのサイズを大きくして、ログファイルのキャッシュの場所をネットワーク共有に設定します。

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> これは、「新しい集中ログサービスの構成を作成するには」の手順で作成した新しい構成です。

サイトレベルの構成の削除を選択すると、サイトではグローバル設定が使用されます。
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 で集中ログサービスのプロバイダーを構成する](configure-providers.md)

[Skype for Business Server 2015 での集中ログサービスのシナリオの構成](configure-scenarios.md)

[Skype for Business 2015 の集中ログサービス](centralized-logging-service.md)

[設定-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[取得-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[新しい-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[削除-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
