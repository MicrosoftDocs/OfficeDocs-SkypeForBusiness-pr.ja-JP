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
localization_priority: Normal
description: この記事では、Microsoft Teams ミーティング の回復ツールを使用する方法について説明します。このツールを使用して、システムが最新でなからサポートされている状態になります。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117495"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、Microsoft Teams ミーティング の回復ツールを使用する方法について説明します。このツールを使用して、システムが最新でなからサポートされている状態になります。 このツールは、Microsoft Teams ミーティング コンソールで "システム構成が最新ではありません" というエラーが表示される場合、またはプッシュ ボタンのリセット 工場出荷時の復元 を実行する前に[適用する必要があります](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>前提条件

最新のMicrosoft Teams ミーティング[インストール パッケージをダウンロード](https://go.microsoft.com/fwlink/?linkid=851168)し、デバイスからアクセスできる USB メモリ スティックまたはネットワーク共有Microsoft Teams ミーティングします。

> [!NOTE]
> MSI からファイルを抽出するには、多くの方法があります。 すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムはすべて許容されます。 そのような方法の 1 つは、 コマンドを使用する方法です。このコマンドは、Microsoft Teams Room インストール パッケージへの完全パスを表し、ファイルの抽出先のフォルダーへの完全パスを表 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` します。

## <a name="running-the-tool"></a>ツールの実行

1) デバイスで管理者アカウントにサインインしMicrosoft Teams ミーティング管理者特権でコマンド プロンプトを起動します。
2) インストール パッケージMicrosoft Teams ミーティングから抽出されたファイルに含まれている にアクセスできるデバイスMicrosoft Teams ミーティング `RecoveryTool.ps1 file` 確認します。 このキットは、前提条件の準備時に使用されるネットワーク共有または USB ドライブにあります。
3) を実行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` します。
4) 出荷時の復元を実行するには:
   1. スクリプトによって求めるメッセージが表示されたら、オプション 2: [リセット] を **選択します**。
   2. 有効BitLocker場合は、スクリプト出力の最後に表示される手順に従って無効にします。
   3. ファクトリの復元を実行します。
      1. アプリを開 **設定、[** セキュリティの更新] **&選択します。**
      2. [回復] タブ **に移動** します。
      3. [この **PC をリセットする] の下にある**[開始 **] を選択します。**
      4. [すべて **削除] を選択し**、[次 **へ] と [リセット** ] を **選択します。**
        > [!WARNING]
        > [Microsoft Teams ミーティングファイルを保持 **する -** アプリと設定を削除しますが、リセットプロセス中に個人用ファイルを保持する] オプションが選択されている場合、Windows使用できなくなる可能性があります。 このオプションは選択しない。
      5. システムは複数回再起動します。 リセットが完了すると、システムは "Windows エクスペリエンス" (OOBE) 画面に表示されます。



## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)