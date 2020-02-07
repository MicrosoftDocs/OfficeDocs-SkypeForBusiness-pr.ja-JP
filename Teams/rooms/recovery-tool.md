---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: v-lanac
author: lanachin
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
description: この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。
ms.openlocfilehash: 452f5d9d15375bec7ac25c07c865add8a01b0345
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831179"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。 このツールは、Microsoft Teams の [ルーム] コンソールに "システム構成の終了" エラーが表示された場合、またはプッシュボタンで[出荷時の復元](https://docs.microsoft.com/microsoftteams/room-systems/rooms-operations#microsoft-teams-rooms-reset-factory-restore)のリセットを実行する前の場合に適用されます。

## <a name="prerequisites"></a>前提条件

最新の[Microsoft Teams ルームインストールパッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、それを USB メモリスティックまたは Microsoft teams 室デバイスにアクセスできるネットワーク共有に抽出します。

> [!NOTE]
> MSI からファイルを抽出する方法は、さまざまな方法で実現できます。 すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムは受け入れられます。 このような方法の1つは`msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` 、 `PathToMsi` Microsoft Teams Room インストールパッケージへの完全パスを示すコマンドを`PathToTarget`使うことです。また、ファイルを抽出するフォルダーのフルパスを表します。

## <a name="running-the-tool"></a>ツールを実行する

1) Microsoft Teams 室のデバイスで管理者アカウントにサインインして、管理者特権のコマンドプロンプトを起動します。
2) Microsoft teams 室のインストールパッケージから抽出されたファイルに含ま`RecoveryTool.ps1 file`れている、microsoft Teams の会議室のデバイスで確認することができます。 キットは、前提条件を準備するときに使用したネットワーク共有または USB ドライブにあります。
3) 実行`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`します。
4) 出荷時の復元を実行している場合は、次の手順に従います。
   - スクリプトによってプロンプトが表示されたら、[オプション 2:**リセット**] を選びます。
   - BitLocker がオンになっている場合は、スクリプト出力の最後に示されている手順に従って、無効にします。
   - 出荷時の復元を実行します。
      - **設定**アプリを開き、[**更新] &** の [セキュリティ] を選択します。
      - [**回復**] タブに移動します。
      - [**この PC をリセット**する] の下で、[**はじめ**に] を選択します。
      - [**すべて削除**]、[**次へ**]、[**リセット**] の順に選択します。
      - システムが複数回再起動します。 リセットが完了すると、Windows OOBE 画面にシステムが表示されます。
5) "古い" システムを修復する場合は、次の操作を行います。
    - スクリプトによってメッセージが表示されたら、[オプション 1:**修復**] を選択します。
    - 完了したら、Microsoft Teams 室のデバイスを再起動します。 自動的に再起動され、2回目の回復が完了します。

> [!NOTE]
> **[自分のファイルを保持する] でアプリと設定を削除**した場合、Microsoft Teams の会議室が使用できなくなるという既知の問題がありますが、Windows のリセットプロセス中に個人用ファイルオプションが選択されたままになります。 このオプション*は使用しないでください。*

## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
