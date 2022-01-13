---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態に更新されません。
ms.openlocfilehash: 6f78f78ab17620a3466da713d813f8320b163a84
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015067"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態に更新されません。 このツールは、Microsoft Teams Rooms コンソールに "システム構成が最新ではありません" というエラーが表示される場合、またはプッシュ ボタンのリセット ファクトリ復元を実行する前に適用[する必要があります](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>前提条件

最新の[Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168)インストール パッケージをダウンロードし、会議室からアクセスできる USB メモリ スティックまたはネットワーク共有Microsoft Teamsします。

> [!NOTE]
> MSI からファイルを抽出するには、多くの方法があります。 すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムはすべて許容されます。 そのような方法の 1 つは、 コマンドを使用する方法です。このコマンドは、Microsoft Teams Room インストール パッケージへの完全パスを表し、ファイルの抽出先のフォルダーへの完全パスを表 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` します。

## <a name="running-the-tool"></a>ツールの実行

1) Microsoft Teams Rooms デバイスで管理者アカウントにサインインし、管理者特権のコマンド プロンプトを起動します。
2) Microsoft Teams Rooms インストール パッケージから抽出されたファイルに含まれているファイルにアクセスできる Microsoft Teams Rooms デバイス `RecoveryTool.ps1` から確認します。 キットは、前提条件の準備時に使用されるネットワーク共有または USB ドライブにあります。
3) を実行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` します。
4) 出荷時の復元を実行するには:
   1. スクリプトによって求めるメッセージが表示されたら、オプション 2: [リセット] を **選択します**。
   2. BitLocker がオンの場合は、スクリプト出力の最後に表示される指示に従って無効にします。
   3. ファクトリの復元を実行します。
      1. アプリを開 **設定** し、[セキュリティの更新 **] &選択します。**
      2. [回復] タブ **に移動** します。
      3. [この **PC をリセットする] の下にある**[開始 **] を選択します。**
      4. [すべて **削除] を選択し**、[次 **へ] と [リセット** ] を **選択します。**
        > [!WARNING]
        > [Microsoft Teamsファイルの保持 Windows **-** アプリと設定を削除しますが、リセットプロセス中に個人用ファイルを保持する] オプションが選択されている場合、Microsoft Teams Rooms デバイスが使用できなくなる可能性があります。 このオプションは選択しない。
      5. システムは複数回再起動します。 リセットが完了すると、システムは "Windowsエクスペリエンス" (OOBE) 画面に表示されます。



## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
