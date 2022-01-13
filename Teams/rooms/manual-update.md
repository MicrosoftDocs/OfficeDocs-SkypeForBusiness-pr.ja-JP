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
description: Microsoft Teams Rooms デバイスを特定のバージョンに手動で更新する方法について説明します。
ms.openlocfilehash: 0b8ec08880d3f8c7ecce28293c92fb6ada901277
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62014997"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Microsoft Teams Rooms デバイスを手動で更新する

Microsoft Teams Rooms アプリは、Microsoft Store を通じて配布されます。 アプリの更新プログラムは、夜間のメンテナンスMicrosoft Store自動的にインストールされます。更新プログラムを取得するには、この方法をお勧めします。 ただし、会議室デバイスがTeamsから更新プログラムを受信できない場合Microsoft Store。 たとえば、セキュリティ ポリシーでは、デバイスがインターネットに接続できない場合や、デバイスからアプリをダウンロードできない場合Microsoft Store。 または、セットアップを実行する前にデバイスを更新し、その間Microsoft Store使用できない場合があります。

Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリの更新 PowerShell スクリプトを使用して、Teams Rooms デバイスを新しいバージョンの Teams Rooms アプリに手動で更新できます。 この記事の手順に従って、会議室デバイスTeams更新します。

> [!NOTE]
> このプロセスでは、Teams Rooms アプリが既にインストールされている Teams Rooms デバイスのみを更新できます。 新しいインストールの実行には使用できません。 また、アプリを以前のバージョンにダウングレードするためにも使用できません。 Teams Rooms アプリの新しいインストールを実行するには、デバイスの製造元に特定のメディアを問い合わせください。

## <a name="step-1-download-the-offline-app-update-script"></a>手順 1: オフライン アプリの更新スクリプトをダウンロードする

まず、オフライン アプリ更新スクリプトの最新バージョンをダウンロードします。 スクリプトをダウンロードするには、 をクリックします <https://go.microsoft.com/fwlink/?linkid=2151817> 。 スクリプトは、デバイスの既定のダウンロード フォルダーにダウンロードされます。

ダウンロードしたファイルは、ダウンロードしたファイルがブロック済みとしてマークWindows。 操作を行わずにスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。 スクリプトのブロックを解除するには、次の操作を行います。

1. エクスプローラーでファイルを右クリックする
2. [プロパティ] **をクリックします。**
3. [ブロック **の解除] を選択する**
4. **[OK] をクリックします。**

PowerShell を使用してスクリプトのブロックを解除するには、「ファイルのブロックを解除 [する」を参照してください](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

オフライン アプリの更新スクリプトがダウンロードされた後、ファイルを Teams デバイスに転送します。 USB ドライブを使用するか、デバイスの管理モードでネットワーク ファイル共有からファイルにアクセスして、デバイスにファイルを転送できます。 デバイスでファイルを保存する場所をメモしてください。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>手順 2: スクリプトを実行して、Teams Rooms アプリを更新する

Skype ユーザー (アプリを実行するユーザー) がまだサインインしている間は、管理者特権のコマンド プロンプトからオフライン アプリ更新スクリプトを実行する必要があります。 Skype ユーザーがまだログインしている間に管理者アカウントにログインして管理者特権のコマンド プロンプトを使用する方法の詳細については、「管理者モードに切り替えて[、Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)アプリがクラッシュした場合に戻る」を参照してください。

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

スクリプトの実行を許可します。 完了すると、スクリプトは Rooms デバイスTeams再起動します。

リモート PowerShell を使用してスクリプトを実行することもできます。 Teams Rooms デバイスでリモート PowerShell を使用する方法の詳細については、「PowerShell を使用したリモート[管理」を参照してください](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>手順 3: アプリが正常に更新されたことを確認する

スクリプトが正常に実行されると、デバイスは Teams に再起動します。

スクリプトで問題が発生した場合は、コマンド ラインで何が問題かを示し、その出力をファイルに記録します。 スクリプトによって提供される指示に従います。 Microsoft サポートに連絡する必要がある場合は、サポート要求と共にログ ファイルを含める必要があります。 スクリプトによって、ログ ファイルへのパスが提供されます。
