---
title: 管理ツールをインストールして開く
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: このトピックでは、Skype for Business の展開と管理に必要な管理ツールをインストールして開く方法について説明します。
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031071"
---
# <a name="install-and-open-administrative-tools"></a>管理ツールをインストールして開く

このトピックでは、Skype for Business Server の展開と管理に必要な管理ツールのインストール方法について説明します。 管理ツールは、Skype for Business Server を実行している各サーバーに既定でインストールされます。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 Active Directory ドメインサービスの準備手順が既に完了していることを確認するために、作成している Skype for Business Server の展開と同じドメインまたはフォレストにあるコンピューターに管理ツールをインストールすることを強くお勧めします。これにより、後でそのコンピューターの管理ツールを使用してトポロジを公開することができます。 また、Skype for Business Server 管理ツールをインストールまたは使用する前に、必要な要件を確認してください。 [Skype For Business server 2019](../../SfBServer2019/plan/system-requirements.md)または[Skype for business server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)の要件に関するドキュメントを参照してください。
 
> [!Important]
> インターネットインフォメーションサービス (IIS) とすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Skype for Business Server ファイルのインストール場所のパスを変更できます。 このパス (OCSCore を含む) にセットアップファイルをインストールすると、その他の Skype for Business Server ファイルもこのドライブに展開されます。 

## <a name="to-install-the-administrative-tools"></a>管理ツールをインストールするには

1. 管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。 Windows で標準ユーザーとしてログオンし、ユーザーアカウント制御 (UAC) が有効になっている場合は、ローカル管理者またはドメインに相当するユーザー名とパスワードの入力を求められます。
2. コンピューターにインストール メディアを配置し、\Setup\amd64\Setup.exe をダブルクリックします。
3. Microsoft Visual C++ の再配布をインストールするように求めるメッセージが表示されたら、[**はい]** をクリックします。
4. [インストール先] ページで、[ **OK**] をクリックします。 ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。

    > [!Important]
    > インターネットインフォメーションサービス (IIS) とすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Skype for Business Server ファイルのインストール場所のパスを変更できます。 このパス (OCSCore を含む) にセットアップファイルをインストールすると、その他の Skype for Business Server ファイルもこのドライブに展開されます。 

5. [使用許諾契約書] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。 続行するにはこのステップが必要です。
6. [展開ウィザード] ページで、[**管理者ツールのインストール**] をクリックします。 
7. インストールが正常に完了したら、[**終了**] をクリックします。

次の手順を使用して、Skype for Business Server のトポロジを展開、構成、またはトラブルシューティングするための管理ツールを開きます。

- [展開ウィザード](#deployment-wizard)
- [トポロジ ビルダー](#topology-builder) 
- [Skype for Business Server コントロール パネル](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理シェル](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>展開ウィザード

次の手順を使用して、展開ウィザードをローカルで起動し、コンポーネントファイルを追加または削除します。

**Skype for Business Server の展開ウィザードを起動するには**

1. Skype for Business Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
2. [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server 展開ウィザード**] の順にクリックします。


## <a name="topology-builder"></a>トポロジ ビルダー 

次の手順を使用して、トポロジビルダーを開き、Skype for Business Server のトポロジに展開するサーバーを定義します。

**Skype for Business Server トポロジビルダーを開いてトポロジを設計するには**

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    > [!NOTE]
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、サーバーに Skype for Business Server をインストールするために必要なトポロジを読み取り、公開、または有効にするには、Domain Admins グループのメンバーであるアカウントを使用する必要があります。e RTCUniversalServerAdmins グループで、アーカイブファイルストアに使用するファイル共有に対するフルコントロールのアクセス許可 (読み取り、書き込み、および変更) を持ち、トポロジビルダーが必要な随意アクセス制御リストを構成できるようにします (Dacl)、またはそれと同等のユーザー権限を持つアカウント。
 
2. トポロジビルダーを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server トポロジビルダー**] の順にクリックします。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネル 

次のいずれかの手順を使用して、Skype for Business Server コントロールパネルを開き、環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理します。

> [!NOTE]
> CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Skype for Business Server コントロールパネルで任意のタスクを実行できます。 他の役割を使用して Skype for Business Server コントロールパネルにログオンすると、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、Skype for Business Server コントロールパネルのアーカイブを管理できます。 役割の詳細については、「[役割ベースのアクセス制御を計画する](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)」を参照してください。 特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。 

**組織のファイアウォールの内側にある任意のコンピューターから [Skype for Business Server] コントロールパネルを開くには**

1. CsAdministrator の役割、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割に割り当てられているユーザーアカウントから、最小画面解像度 1024 x 768 を使用して、内部展開の任意のコンピューターにログオンします。

    > [!IMPORTANT]
    > 管理の簡単な uniform resource locator (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネットブラウザーから、Skype for Business Server コントロールパネルにアクセスできます。 管理の簡易 URL の構成の詳細については、「 [Planning for Simple urls](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) 」および「 [Edit Or configure simple urls](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx)」を参照してください。 

2. ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

**Skype for business Server を実行しているコンピューターで Skype for Business Server コントロールパネルを開くには**

1. CsAdministrator の役割のメンバーであるか、タスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割のメンバーであるユーザーアカウントから、Skype for Business Server をインストールしたコンピューターにログオンします。または、少なくともSkype for Business Server の管理ツール。 設定を構成するには、コンピューターの最小画面解像度を 1024 x 768 にする必要があります。
2. Skype for Business Server コントロールパネルを起動します。 [**スタート**]、[**すべてのプログラム**]、[**管理ツール**] の順にポイントし、[ **skype for business server**] をポイントして、[ **skype for business server コントロールパネル**] をクリックします。

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル 

次の手順を使用して、コマンドラインを使用して、環境内のサーバー、ユーザー、クライアント、デバイスを管理するための Skype for Business Server 管理シェルを開きます。

> [!NOTE]
> CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Skype for Business Server 管理シェルで任意のタスクを実行できます。 特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。 たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。 役割の詳細については、「[役割ベースのアクセス制御を計画する](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)」を参照してください。 特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<br/><br/>コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。 

**Skype for Business Server 管理シェルを開くには**

Skype for Business Server 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定では Skype for Business Server のコマンドレットを実行できません。 Windows PowerShell で Skype for Business Server のコマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。

`Import-Module Lync`

Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business server**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。
