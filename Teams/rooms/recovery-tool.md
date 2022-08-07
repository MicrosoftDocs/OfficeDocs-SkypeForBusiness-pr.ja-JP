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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: この記事では、古いシステムをサポートされている状態にするために使用する、Microsoft Teams Roomsの回復ツールを使用する方法について説明します。
ms.openlocfilehash: c50b59ff4ed1ee997b990b0776ef4a7ee0ac29c2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271162"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、古いシステムをサポートされている状態にするために使用する、Microsoft Teams Roomsの回復ツールを使用する方法について説明します。 このツールは、Microsoft Teams Rooms コンソールで "システム構成が最新ではない" というエラーが表示された場合、またはプッシュ ボタンリセット[ファクトリの復元](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)を実行する前に適用する必要があります。

## <a name="prerequisites"></a>前提条件

最新の[Microsoft Teams Rooms インストール パッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、Microsoft Teams Roomsにアクセスできる USB メモリ スティックまたはネットワーク共有に展開します。

> [!NOTE]
> MSI からファイルを抽出することは、多くの方法で実現できます。 すべてのファイルを抽出し、そのディレクトリ構造を保持するメカニズムは許容されます。 そのような方法の 1 つは、Microsoft Teams Room インストール パッケージへの完全なパスを表し`PathToTarget`、抽出するファイルのフォルダーへの完全なパスを表すコマンド`msiexec /a PathToMsi /qb TARGETDIR=PathToTarget``PathToMsi`を使用することです。

## <a name="running-the-tool"></a>ツールの実行

1) Microsoft Teams Rooms デバイスの管理者アカウントにサインインし、管理者特権でコマンド プロンプトを起動します。
2) Microsoft Teams Rooms デバイスから、Microsoft Teams Rooms インストール パッケージから抽出されたファイルに含まれるファイルにアクセス`RecoveryTool.ps1`できることを確認します。 このキットは、前提条件を準備するときに使用されるネットワーク共有または USB ドライブにあります。
3) 実行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`します。
4) ファクトリの復元を実行するには:
   1. スクリプトによってプロンプトが表示されたら、オプション 2: **リセット** を選択します。
   2. BitLocker がオンになっている場合は、スクリプト出力の最後に示されている手順に従って無効にします。
   3. ファクトリの復元を実行します。
      1. **設定** アプリを開き、[**セキュリティの更新&**] を選択します。
      2. **[回復]** タブに移動します。
      3. [**この PC をリセットする**] の下にある [**作業の開始**] を選択します。
      4. [**すべて削除]** を選択し、[**次へ**] と [リセット] の順に選択 **します**。
        > [!WARNING]
        > [ファイルを **保持する - アプリと設定を削除しますが、個人用ファイルを保持** する] オプションが Windows リセット プロセス中に選択されている場合、Microsoft Teams Rooms デバイスは使用できなくなる可能性があります。 このオプションは選択しないでください。
      5. システムは複数回再起動します。 リセットが完了すると、システムは Windows の "既定のエクスペリエンス" (OOBE) 画面に表示されます。



## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
