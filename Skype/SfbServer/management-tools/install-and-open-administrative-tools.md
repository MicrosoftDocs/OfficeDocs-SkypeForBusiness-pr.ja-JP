---
title: 管理ツールのインストールおよび起動
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: このトピックでは、展開および管理に必要な管理ツールをインストールして開く方法についてSkype for Business。
ms.openlocfilehash: e3df2fd72cafbbf724baed3f86d0b62d74583348
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384195"
---
# <a name="install-and-open-administrative-tools"></a>管理ツールのインストールおよび起動

このトピックでは、展開および管理に必要な管理ツールをインストールする方法についてSkype for Business Server。 管理ツールは、管理ツールを実行している各サーバーに既定でSkype for Business Server。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 Active Directory ドメイン サービスの準備手順が既に完了し、後でそのコンピューターの管理ツールを使用してトポロジを公開するには、作成する Skype for Business Server 展開と同じドメインまたはフォレスト内のコンピューターに管理ツールをインストールすることを強く推奨します。 また、管理ツールをインストールまたは使用する前に、必要な要件Skype for Business Server確認してください。 [2019 または Skype for Business Server 2015](../../SfBServer2019/plan/system-requirements.md) の要件[Skype for Business Server参照](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)してください。
 
> [!Important]
> システム ドライブ以外のドライブで インターネット インフォメーション サービス (IIS) とすべての Web サービスを見つける必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所パスを変更できます。 セットアップ ファイルをこのパス (OCSCore.msi を含む) にインストールすると、Skype for Business Server ファイルの残りの部分もこのドライブに展開されます。 

## <a name="to-install-the-administrative-tools"></a>管理ツールをインストールするには

1. 管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。 Windows で標準ユーザーとしてログオンし、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者またはドメインと同等のユーザー名とパスワードを求めるメッセージが表示されます。
2. コンピューターにインストール メディアを配置し、\Setup\amd64\Setup.exe をダブルクリックします。
3. 配布可能なアプリケーションをインストールするように求Microsoft Visual C++場合は、[はい] をクリック **します**。
4. [インストール場所] ページで、[OK] を **クリックします**。 ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。

    > [!Important]
    > システム ドライブ以外のドライブで インターネット インフォメーション サービス (IIS) とすべての Web サービスを見つける必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所パスを変更できます。 セットアップ ファイルをこのパス (OCSCore.msi を含む) にインストールすると、Skype for Business Server ファイルの残りの部分もこのドライブに展開されます。 

5. [使用許諾契約書] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。続行するにはこのステップが必要です。
6. [展開ウィザード] ページで、[管理者ツールの **インストール] をクリックします**。 
7. インストールが正常に完了したら、[**終了**] をクリックします。

次の手順を使用して、管理ツールを開き、トポロジを展開、構成、またはトラブルシューティングSkype for Business Serverします。

- [展開ウィザード](#deployment-wizard)
- [トポロジ ビルダー](#topology-builder) 
- [Skype for Business Server コントロール パネル](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理シェル](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>展開ウィザード

次の手順を使用して、展開ウィザードをローカルで開始して、コンポーネント ファイルを追加または削除します。

**展開ウィザードをSkype for Business Serverするには**

1. ドメイン管理者グループおよび RTCUniversalServerAdmins グループのメンバー Skype for Business Server展開ウィザードがインストールされているコンピューターにログオンします。
2. [**スタート] ボタン**、[**すべてのプログラム] を** クリックし、[Skype for Business Server] **をクリック** し、[展開ウィザードSkype for Business Server **クリックします**。


## <a name="topology-builder"></a>トポロジ ビルダー 

トポロジ ビルダーを開き、トポロジ に展開するサーバーを定義するには、次のSkype for Business Serverします。

**トポロジ ビルダーを開Skype for Business Serverトポロジを設計するには**

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    > [!NOTE]
    > トポロジを定義するには、ローカル の Users グループのメンバーですが、サーバーに Skype for Business Server をインストールするために必要なトポロジの読み取り、公開、または有効化を行うアカウントを使用して、Domain Admins グループのメンバーであり、RTCUniversalServerAdmins グループのメンバーであり、完全な制御権限を持つアカウントを使用する必要があります (つまり、 アーカイブ ファイル ストアで使用するファイル共有の読み取り、書き込み、変更) を行い、トポロジ ビルダーが必要な任意アクセス制御リスト (DACL) または同等のユーザー権限を持つアカウントを構成できます。
 
2. トポロジ ビルダーの開始: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business Server] を **クリック** し、[トポロジ **ビルダー Skype for Business Serverクリックします**。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネル 

次のいずれかの手順を使用して、Skype for Business Server コントロール パネルを開いて、環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理します。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用して、コントロール パネルのタスクSkype for Business Serverできます。 他の役割を使用して、Skype for Business Serverコントロール パネルにログオンして、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、管理コントロール パネルでアーカイブSkype for Business Serverできます。 役割の詳細については、「役割ベースの [アクセス制御の計画」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。 

**組織のファイアウォールSkype for Business Server任意のコンピューターからコントロール パネルを開く方法**

1. CsAdministrator 役割またはタスクを実行するための適切なユーザー権限とアクセス許可を持つ他の役割に割り当てられているユーザー アカウントから、最小画面解像度が 1024 x 768 の内部展開の任意のコンピューターにログオンします。

    > [!IMPORTANT]
    > 管理簡易統一リソース ロケーター (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネット ブラウザーから Skype for Business Server コントロール パネルにアクセスできます。 管理簡易 URL の構成の詳細については、「簡易 URL の計画 [」](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) および「簡易 URL の編集または構成 [」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls)。 

2. ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

**コンピューターで Skype for Business Server コントロール パネルを開Skype for Business Server**

1. CsAdministrator 役割またはタスクの適切なユーザー権限とアクセス許可を持つ他の役割のメンバーであるユーザー アカウントから、Skype for Business Server をインストールしたコンピューターにログオンするか、少なくとも Skype for Business Server 管理ツールにログオンします。 設定を構成するには、コンピューターの最小画面解像度が 1024 x 768 である必要があります。
2. スタートSkype for Business Serverコントロール パネル: [**スタート] を** クリックし、[すべてのプログラム] をクリックし、[管理ツール] をポイントし、[Skype for Business Server] をポイントし、[コントロール パネルSkype for Business Server **クリックします**。

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル 

コマンド ラインを使用して、Skype for Business Server、ユーザー、クライアント、およびデバイスを管理するには、次の手順を実行します。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用して、管理シェルで任意のSkype for Business Server実行できます。 特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。 たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。 役割の詳細については、「役割ベースの [アクセス制御の計画」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<br/><br/>コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。 

**管理シェルをSkype for Business Serverするには**

管理シェルではなくWindows PowerShellウィンドウを開Skype for Business Server既定では、このコマンドレットをSkype for Business Serverできません。 サーバー内から Skype for Business Server コマンドレットをWindows PowerShell、次のコマンド プロンプトにWindows PowerShellします。

`Import-Module Lync`

管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business Server] を **クリック** し、[管理シェルSkype for Business Server **クリックします**。