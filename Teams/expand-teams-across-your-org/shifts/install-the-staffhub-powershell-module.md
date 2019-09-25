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
description: Microsoft StaffHub PowerShell モジュールのプレリリース版をインストールして接続する方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142036"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順に従って、プレリリース版の Microsoft StaffHub PowerShell モジュールをインストールして接続します。 これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>プレリリース版の Microsoft StaffHub PowerShell モジュールをインストールする

1. Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。
    > [!NOTE]
    > 最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。 
2. 次の操作を実行して、プレリリース版の StaffHub PowerShell モジュールをインストールします。

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. 警告メッセージが表示されることがあります。

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    「 `Y`」と入力し`Enter`て、をクリックします。
 
4. Windows PowerShell を終了します。

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールに接続する

1. 次のコマンドを実行します。

    ```
    Connect-StaffHub
    ```

2. メッセージが表示されたら、グローバル管理者としてログインします。

## <a name="related-topics"></a>関連トピック

- [Microsoft StaffHub PowerShell リファレンス](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Microsoft StaffHub のチームを Teams の Shifts に移動する](move-staffhub-teams-to-shifts-in-teams.md)
