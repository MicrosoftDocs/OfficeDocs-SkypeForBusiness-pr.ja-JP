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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80290e6b8a1ce4de834a000148d60b2c5ef89d
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775076"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

> [!IMPORTANT]
> 2019年12月31日有効な場合、Microsoft StaffHub は廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 StaffHub は、2019年12月31日にすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。 これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

1. [StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub)をダウンロードします。
2. Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。
    > [!NOTE]
    > 最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。
3. 次のコマンドを実行します。

    ```
    $ENV:PSModulePath
    ```
4. 出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。 フォルダーがない場合は、フォルダーを作成します。
5. StaffHub PowerShell モジュールのインストールを許可するには、次を実行します。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
6. 次を実行します&lt;。&gt;ここで、path は手順3からの出力のパスです。 たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。

    各コマンドは別々に実行してください。

    ```
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Windows PowerShell を終了します。
8. Windows PowerShell 3.0 以降をグローバル管理者として開き、次の操作を実行します。

    ```
    Install-Module -Name MicrosoftStaffHub

## Connect to the Microsoft StaffHub PowerShell module

1. Run the following:

    ```
    Connect-StaffHub
    ```

2. When you're prompted, log in as a global admin.

## Related topics

- [Microsoft StaffHub PowerShell reference](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Move your Microsoft StaffHub teams to Shifts in Teams](move-staffhub-teams-to-shifts-in-teams.md)
