---
title: StaffHub PowerShell モジュールをインストールする
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell モジュールをインストールして接続する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245917"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。 これは、PowerShell を使用して StaffHub を管理し、StaffHub teams を Microsoft Teams に移動するために必要となります。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

1. [StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)をダウンロードします。 
2. Windows PowerShell 3.0 以降を管理者として開きます。 これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。
3. 次のコマンドを実行します。

    ```
    $ENV:PSModulePath
    ```

4. 出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。 フォルダーがない場合は、フォルダーを作成します。
5. 次を実行します&lt;。&gt;ここで、path は手順2の出力のパスです。 たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールに接続する

1. 次のコマンドを実行します。

    ```
    Connect-StaffHub
    ```

2. メッセージが表示されたら、グローバル管理者としてログインします。

## <a name="related-topics"></a>関連トピック

- [Microsoft StaffHub PowerShell リファレンス](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Microsoft StaffHub のチームを Teams の Shifts に移動する](move-staffhub-teams-to-shifts-in-teams.md)
