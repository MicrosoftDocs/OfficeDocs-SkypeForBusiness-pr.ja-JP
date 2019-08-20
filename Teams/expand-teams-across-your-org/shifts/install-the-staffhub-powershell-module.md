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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464667"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。 これは、PowerShell を使用して StaffHub を管理し、StaffHub teams を Microsoft Teams に移動するために必要となります。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell モジュールをインストールする

1. Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。
    > [!NOTE]
    > 最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。 
2. 次の操作を実行して、現在の安定したバージョンの StaffHub PowerShell モジュールをインストールします。

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    このコマンドは、最新バージョンをインストールする必要がある場合にのみ実行できます。これは、現在の安定バージョンよりも不安定な可能性があります。`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > 不安定な状態で、最新バージョンのインストール中にエラーが発生した場合は、次の操作を実行できます。`Install-Module PowershellGet -Force`

3. 警告メッセージが表示されることがあります。

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

を`Y`入力し`Enter`て、をクリックします。
 
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
