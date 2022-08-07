---
title: Microsoft Teams Rooms デバイスを手動で更新する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Microsoft Teams Rooms デバイスを特定のバージョンに手動で更新する方法について説明します。
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267642"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Microsoft Teams Rooms デバイスを手動で更新する

Microsoft Teams Rooms アプリは Microsoft Store を通じて配布されます。 アプリへの更新は、夜間のメンテナンス中に Microsoft Store から自動的にインストールされます。これは、更新プログラムを取得するために推奨される方法です。 ただし、Teams Rooms デバイスが Microsoft Store から更新プログラムを受信できない状況もあります。 たとえば、セキュリティ ポリシーでは、デバイスがインターネットに接続できない場合や、Microsoft Store からアプリをダウンロードできない場合があります。 または、セットアップを実行する前にデバイスを更新し、その間に Microsoft Store を使用できない場合もあります。

Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリの PowerShell 更新スクリプトを使用して、Teams Rooms デバイスをTeams Rooms アプリの新しいバージョンに手動で更新できます。 この記事の手順に従って、Teams Rooms デバイスを手動で更新します。

> [!NOTE]
> このプロセスでは、Teams Rooms アプリが既にインストールされているTeams Rooms デバイスのみを更新できます。 新しいインストールを実行するために使用することはできません。 また、アプリを古いバージョンにダウングレードするために使用することはできません。 Teams Rooms アプリの新しいインストールを実行するには、デバイスに固有のメディアについては、デバイスの製造元にお問い合わせください。

## <a name="step-1-download-the-offline-app-update-script"></a>手順 1: オフライン アプリ更新スクリプトをダウンロードする

まず、オフライン アプリ更新スクリプトの最新バージョンをダウンロードします。 スクリプトをダウンロードするには、をクリックします <https://go.microsoft.com/fwlink/?linkid=2151817>。 スクリプトは、デバイス上の既定のダウンロード フォルダーにダウンロードされます。

ダウンロードしたファイルは、Windows によってブロック済みとしてマークされる場合があります。 対話なしでスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。 スクリプトのブロックを解除するには、次の操作を行います。

1. エクスプローラーでファイルを右クリックします
2. **[プロパティ**] をクリックします
3. **[ブロック解除]** を選択する
4. [ **OK] をクリックします。**

PowerShell を使用してスクリプトのブロックを解除するには、「 [ブロック解除-ファイル](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)」を参照してください。

オフライン アプリ更新スクリプトがダウンロードされたら、Teams Rooms デバイスにファイルを転送します。 デバイスにファイルを転送するには、USB ドライブを使用するか、デバイスの管理 モードでネットワーク ファイル共有からファイルにアクセスします。 デバイス上のファイルを保存する場所に注意してください。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>手順 2: スクリプトを実行してTeams Rooms アプリを更新する

Skype ユーザー (アプリが実行されているユーザー) がまだサインインしている間は、オフライン アプリ更新スクリプトを管理者特権のコマンド プロンプトから実行する必要があります。 Skype ユーザーがまだログインしている間に管理者特権のコマンド プロンプトを使用するために管理者アカウントにログインする方法の詳細については、「[管理 モードへの切り替えと、Microsoft Teams Rooms アプリがクラッシュしたときに戻る](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)」を参照してください。

管理者特権のコマンド プロンプトからスクリプトを実行するには、次の操作を行います。

1. 管理 モードに切り替える
2. [スタート] アイコンをクリックし、「**コマンド プロンプト」** と入力して、[**管理者として実行**] を選択します。
3. スクリプトへの完全なパスとスクリプト ファイルの名前を含む次のコマンド `<path to script>` を実行します。

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

たとえば、スクリプト ファイルが存在 `C:\Users\Admin\Downloads`し、スクリプト ファイル名が指定されている場合は `MTR-Update-4.5.6.7.ps1`、次のコマンドを実行します。

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

スクリプトの実行を許可します。 完了すると、スクリプトはTeams Roomsデバイスを再起動します。

リモート PowerShell を使用してスクリプトを実行することもできます。 Teams Rooms デバイスでリモート PowerShell を使用する方法の詳細については、「[PowerShell を使用したリモート管理](rooms-operations.md#remote-management-using-powershell)」を参照してください。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>手順 3: アプリが正常に更新されたことを確認する

スクリプトが正常に実行されると、デバイスはTeams Rooms アプリに再起動します。

スクリプトで問題が発生した場合は、コマンド ラインで問題が何であるかを示し、その出力をファイルに記録します。 スクリプトで提供される指示に従います。 Microsoft サポートに問い合わせる必要がある場合は、サポート リクエストと共にログ ファイルを含める必要があります。 このスクリプトでは、ログ ファイルへのパスが提供されます。
