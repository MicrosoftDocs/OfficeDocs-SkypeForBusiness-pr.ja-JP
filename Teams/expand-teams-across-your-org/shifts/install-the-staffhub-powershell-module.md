---
title: StaffHub PowerShell モジュールをインストールする
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell モジュールをインストールして接続する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75ed6840b409f391b87759e2004c0f1ea475ce69
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827565"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

> [!IMPORTANT]
> 2019 年 12 月 31 日より、Microsoft StaffHub が廃止されます。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2019 年 12 月 31 日以降すべてのユーザーがご利用できなくなります。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。 これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

1. [StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub)をダウンロードします。
2. Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。
    > [!NOTE]
    > 最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。
3. 次のコマンドを実行します。

    ```PowerShell
    $ENV:PSModulePath
    ```
4. 出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。 フォルダーがない場合は、フォルダーを作成します。
5. StaffHub PowerShell モジュールのインストールを許可するには、次を実行します。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. 次を実行します&lt;。&gt;ここで、path は手順3からの出力のパスです。 たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。

    各コマンドは別々に実行してください。

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Windows PowerShell を終了します。
8. Windows PowerShell 3.0 以降をグローバル管理者として開き、次の操作を実行します。

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールに接続する

1. 次のコマンドを実行します。

    ```PowerShell
    Connect-StaffHub
    ```

2. メッセージが表示されたら、グローバル管理者としてログインします。

## <a name="related-topics"></a>関連トピック

- [Microsoft StaffHub PowerShell リファレンス](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Microsoft StaffHub のチームを Teams の Shifts に移動する](move-staffhub-teams-to-shifts-in-teams.md)
