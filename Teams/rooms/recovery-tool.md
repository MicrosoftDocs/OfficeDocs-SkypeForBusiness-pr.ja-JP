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
description: この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態でサポートされている状態になります。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117495"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態でサポートされている状態になります。 このツールは、Microsoft Teams Rooms 本体に "システム 構成が最新ではありません" というエラーが表示される場合、またはプッシュ ボタンのリセット出荷時の復元を実行する前に適用する [必要があります](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>前提条件

最新の [Microsoft Teams Rooms インストール パッケージを](https://go.microsoft.com/fwlink/?linkid=851168) ダウンロードし、Microsoft Teams Rooms デバイスからアクセス可能な USB メモリ スティックまたはネットワーク共有に展開します。

> [!NOTE]
> MSI からファイルを抽出するには、多くの方法があります。 すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムはすべて許容されます。 そのような方法の 1 つは、Microsoft Teams Room インストール パッケージへのフル パスを表し、ファイルを抽出するフォルダーへのフル パスを表すコマンドを `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 使用する方法です。

## <a name="running-the-tool"></a>ツールを実行する

1) Microsoft Teams Rooms デバイスで管理者アカウントにサインインし、管理者特権のコマンド プロンプトを起動します。
2) Microsoft Teams Rooms のインストール パッケージから抽出されたファイルに含まれている、アクセスできる Microsoft Teams Rooms デバイス `RecoveryTool.ps1 file` から確認します。 このキットは、前提条件を準備するときに使用されるネットワーク共有または USB ドライブにあります。
3) [実行] を選択します `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 出荷時の復元を実行するには、次の手順を実行します。
   1. スクリプトによって求めるメッセージが表示されたら、オプション 2: [リセット] を **選択します**。
   2. BitLocker がオンの場合は、スクリプト出力の最後に表示される指示に従って無効にします。
   3. 出荷時の復元を実行します。
      1. [設定] **アプリを開** き、[セキュリティの **更新&選択する**
      2. [回復] タブ **に移動** します。
      3. [この **PC をリセットする] の下** の [開始 **] を選ぶ**
      4. [すべて **削除]、次に**[次へ **]、および** [リセット] の順に **選択します。**
        > [!WARNING]
        > Microsoft Teams Rooms デバイスは、[ファイルを保持] **-** [アプリと設定を削除します] を選択した場合、使用できなくなる可能性がありますが、Windows のリセット プロセス中に個人用ファイルオプションが選択された状態を維持します。 このオプションは選択しない。
      5. システムは複数回再起動します。 リセットが完了すると、システムは Windows の "既定のエクスペリエンス" (OOBE) 画面に表示されます。



## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)