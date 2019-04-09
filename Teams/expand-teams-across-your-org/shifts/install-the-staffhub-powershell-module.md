---
title: StaffHub PowerShell モジュールをインストールします。
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: インストールし、マイクロソフトの StaffHub の PowerShell モジュールに接続する方法を説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555135"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub の PowerShell モジュールをインストールします。

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 マイクロソフトのチームに StaffHub 機能が進められています。 今日では、チームには、スケジュール管理のためのシフトのアプリケーションが含まれていて、その他の機能が時間の経過と共に展開されます。 StaffHub は、2019 年 10 月 1 日ですべてのユーザーの作業を停止します。 StaffHub を開こうとするとすべての人がチームをダウンロードすることを指示するメッセージ表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

インストールし、マイクロソフトの StaffHub の PowerShell モジュールへの接続をこの資料の手順を使用します。 この PowerShell を使用して StaffHub を管理して、マイクロソフトのチーム、StaffHub チームに移動する必要があります。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub の PowerShell モジュールをインストールします。

1. [StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)をダウンロードします。 
2. 3.0 以降は、管理者として、Windows PowerShell を開きます。 これを行うには、[**スタート**] ボタン、 **Windows PowerShell**を入力、 **Windows PowerShell**を右クリックし [**管理者として実行**します。
3. 次のコマンドレットを実行します。

    ```
    $ENV:PSModulePath
    ```

4. 出力フォルダーのパスを確認し、次の手順に進む前に、コンピューター上のパスのすべてのフォルダーが存在するかどうかを確認します。 フォルダーが存在しない場合は、それらを作成します。
5. 、次を実行、&lt;パス&gt;は、手順 2 からの出力のパス。 たとえば、パスは、C:\Users\User1\Documents\WindowsPowerShell\Modules のようになります。

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールへの接続します。

1. 次のコマンドレットを実行します。

    ```
    Connect-StaffHub
    ```

2. グローバル管理者としてメッセージが表示されたら、ログします。

## <a name="related-topics"></a>関連トピック

- [Microsoft StaffHub PowerShell 参照](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Microsoft StaffHubのチームを、TeamsのShiftsに移動します](move-staffhub-teams-to-shifts-in-teams.md)
