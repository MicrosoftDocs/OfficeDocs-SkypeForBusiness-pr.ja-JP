---
title: デバイスを手動Microsoft Teams ミーティングする
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: デバイスを特定のバージョンに手動Microsoft Teams ミーティング更新する方法について説明します。
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117515"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>デバイスを手動Microsoft Teams ミーティングする

アプリMicrosoft Teams ミーティングは、アプリを通じて配布Microsoft Store。 アプリの更新プログラムは、夜間のメンテナンス中Microsoft Storeから自動的にインストールされます。これは、更新プログラムを取得するために推奨される方法です。 ただし、一部のデバイスでは、Teams ミーティングデバイスから更新プログラムを受信できない場合Microsoft Store。 たとえば、セキュリティ ポリシーでは、デバイスがインターネットに接続できない場合や、デバイスからアプリをダウンロードできない場合Microsoft Store。 または、セットアップを実行する前にデバイスを更新する必要がある場合があります。その間Microsoft Storeは使用できません。

Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリ更新 PowerShell スクリプトを使用して、Teams ミーティング デバイスを新しいバージョンの Teams ミーティング アプリに手動で更新できます。 この記事の手順に従って、デバイスを手動でTeams ミーティングします。

> [!NOTE]
> このプロセスでは、既にインストールされているTeams ミーティングデバイスを更新Teams ミーティング更新できます。 新しいインストールの実行には使用できません。 また、アプリを以前のバージョンにダウングレードするためにも使用できません。 Teams ミーティング アプリの新しいインストールを実行するには、デバイスの製造元に特定のメディアを問い合わせ、または「インストール メディアを準備する」[を参照してください](console.md#prepare-the-installation-media)。

## <a name="step-1-download-the-offline-app-update-script"></a>手順 1: オフライン アプリの更新スクリプトをダウンロードする

まず、オフライン アプリ更新スクリプトの最新バージョンをダウンロードします。 スクリプトをダウンロードするには、 をクリックします <https://go.microsoft.com/fwlink/?linkid=2151817> 。 スクリプトは、デバイスの既定のダウンロード フォルダーにダウンロードされます。

ダウンロードしたファイルは、ダウンロードしたファイルがブロック済みとしてマークWindows。 操作を行わずにスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。 スクリプトのブロックを解除するには、次の操作を行います。

1. エクスプローラーでファイルを右クリックする
2. [プロパティ] **をクリックします。**
3. [ブロック **の解除] を選択する**
4. **[OK] をクリックします。**

PowerShell を使用してスクリプトのブロックを解除するには、「ファイルのブロックを解除 [する」を参照してください](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

オフライン アプリの更新スクリプトがダウンロードされた後、ファイルをデバイスにTeams ミーティングします。 USB ドライブを使用するか、デバイスの管理モードでネットワーク ファイル共有からファイルにアクセスして、デバイスにファイルを転送できます。 デバイスでファイルを保存する場所をメモしてください。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>手順 2: スクリプトを実行してアプリをTeams ミーティングする

オフライン アプリの更新スクリプトは、管理者特権でコマンド プロンプトから実行する必要があります。Skype ユーザー (アプリを実行するユーザー) はまだサインインしています。 Skype ユーザーがまだログインしている間に管理者アカウントにログインして管理者特権のコマンド プロンプトを使用する方法の詳細については、「管理者モードに切り替えて[、Microsoft Teams ミーティング](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)アプリが実行されているときに戻る」を参照してください。

管理者特権のコマンド プロンプトからスクリプトを実行するには、次の操作を行います。

1. 管理モードに切り替える
2. [スタート] アイコンをクリックし、「コマンド プロンプト」 **と入力** して、[管理者として **実行] を選択します。**
3. 次のコマンドを実行 `<path to script>` します。スクリプトへの完全なパスとスクリプト ファイルの名前が含まれます。

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

たとえば、スクリプト ファイルが にあり、スクリプト ファイル名が である場合は、 `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 次のコマンドを実行します。

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

スクリプトの実行を許可します。 完了すると、スクリプトはデバイスを再起動Teams ミーティングします。

リモート PowerShell を使用してスクリプトを実行することもできます。 デバイスでリモート PowerShell を使用する方法の詳細Teams ミーティング PowerShell を使用したリモート[管理に関するページを参照してください](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>手順 3: アプリが正常に更新されたことを確認する

スクリプトが正常に実行されると、デバイスは新しいアプリTeams ミーティングされます。

スクリプトで問題が発生した場合は、コマンド ラインで問題が発生したかどうかを示し、その出力をファイルに記録します。 スクリプトによって提供される指示に従います。 Microsoft サポートに連絡する必要がある場合は、サポート要求と共にログ ファイルを含める必要があります。 スクリプトによって、ログ ファイルへのパスが提供されます。