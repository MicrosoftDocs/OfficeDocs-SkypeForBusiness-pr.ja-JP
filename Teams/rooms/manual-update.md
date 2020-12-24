---
title: Microsoft Teams の会議室デバイスを手動で更新する
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
description: Microsoft Teams Rooms デバイスを特定のバージョンに手動で更新する方法について説明します。
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731395"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Microsoft Teams の会議室デバイスを手動で更新する

Microsoft Teams Rooms アプリは、Microsoft Store を通じて配布されます。 夜間のメンテナンス中に、アプリの更新プログラムが Microsoft Store から自動的にインストールされます。これは、更新プログラムを取得するために推奨される方法です。 ただし、Teams Rooms デバイスが Microsoft Store から更新プログラムを受信できない場合もあります。 たとえば、セキュリティ ポリシーによって、デバイスがインターネットに接続できない場合や、Microsoft Store からアプリをダウンロードできない場合があります。 または、セットアップを実行する前にデバイスを更新して、Microsoft Store を利用できない場合があります。

Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリの更新 PowerShell スクリプトを使用して、Teams Rooms デバイスを新しいバージョンの Teams Rooms アプリに手動で更新できます。 Teams Rooms デバイスを手動で更新するには、この記事の手順に従います。

> [!NOTE]
> このプロセスでは、Teams Rooms アプリが既にインストールされている Teams Rooms デバイスのみを更新できます。 新しいインストールを実行するために使用できません。 また、アプリを以前のバージョンにダウングレードするためにも使用できません。 Teams Rooms アプリの新しいインストールを実行するには、デバイスの製造元に問い合わせ、固有のメディアを確認するか、「インストール メディアを準備する [」を参照してください](console.md#prepare-the-installation-media)。

## <a name="step-1-download-the-offline-app-update-script"></a>手順 1: オフライン アプリの更新スクリプトをダウンロードする

まず、オフライン アプリの更新スクリプトの最新バージョンをダウンロードします。 スクリプトをダウンロードするには、[. <https://go.microsoft.com/fwlink/?linkid=2151817> スクリプトは、デバイスの既定のダウンロード フォルダーにダウンロードされます。

ダウンロードしたファイルは、Windows によってブロック済みとしてマークされる場合があります。 操作を行わずにスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。 スクリプトのブロックを解除するには、次の操作を行います。

1. エクスプローラーでファイルを右クリックする
2. [プロパティ] を **クリックする**
3. [ブロック **解除] を選択する**
4. [OK] を **クリックする**

PowerShell を使用してスクリプトのブロックを解除するには、「ファイルのブロック [を解除する」を参照してください](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

オフライン アプリの更新スクリプトがダウンロードされた後、ファイルを Teams Rooms デバイスに転送します。 デバイスの管理モードで、USB ドライブを使用するか、ネットワーク ファイル共有からファイルにアクセスして、デバイスにファイルを転送できます。 デバイスでファイルを保存する場所をメモしてください。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>手順 2: スクリプトを実行して Teams Rooms アプリを更新する

オフライン アプリの更新スクリプトは、Skype ユーザー (アプリを実行するユーザー) がまだサインインしている間、管理者特権のコマンド プロンプトから実行する必要があります。 Skype ユーザーがまだログインしている間に管理者アカウントにログインして管理者特権のコマンド プロンプトを使用する方法の詳細については [、「Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)アプリの実行中に管理モードに切り替え、戻る」を参照してください。

管理者特権でコマンド プロンプトからスクリプトを実行するには、次の操作を行います。

1. 管理モードに切り替える
2. [スタート] アイコンをクリックし、「コマンド プロンプト **」と入力** して、[管理者として **実行] を選択します。**
3. スクリプトのフル パスとスクリプト ファイルの名前を含む `<path to script>` 次のコマンドを実行します。

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

たとえば、スクリプト ファイルが場所にあり、スクリプト ファイル名が次の `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 場合は、次のコマンドを実行します。

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

スクリプトの実行を許可します。 完了すると、スクリプトは Teams Rooms デバイスを再起動します。

リモート PowerShell を使用してスクリプトを実行することもできます。 Teams 会議室デバイスでのリモート PowerShell の使用の詳細については、「PowerShell を使用したリモート [管理」を参照してください](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>手順 3: アプリが正常に更新されたことを確認する

スクリプトが正常に実行されると、デバイスは Teams Rooms アプリに再起動します。

スクリプトで問題が発生した場合は、コマンド ラインの問題を示し、その出力をファイルに記録します。 スクリプトで提供される指示に従います。 Microsoft サポートに連絡する必要がある場合は、サポート要求と共にログ ファイルを必ず含める必要があります。 スクリプトによって、ログ ファイルへのパスが提供されます。
