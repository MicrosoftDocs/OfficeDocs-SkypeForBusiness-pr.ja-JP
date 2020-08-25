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
description: この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021725"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する

この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。 このツールは、Microsoft Teams の [ルーム] コンソールに "システム構成の終了" エラーが表示された場合、またはプッシュボタンで [出荷時の復元](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)のリセットを実行する前の場合に適用されます。

## <a name="prerequisites"></a>前提条件

最新の [Microsoft Teams ルームインストールパッケージ](https://go.microsoft.com/fwlink/?linkid=851168) をダウンロードし、それを USB メモリスティックまたは Microsoft teams 室デバイスにアクセスできるネットワーク共有に抽出します。

> [!NOTE]
> MSI からファイルを抽出する方法は、さまざまな方法で実現できます。 すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムは受け入れられます。 このような方法の1つは `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` 、 `PathToMsi` Microsoft Teams Room インストールパッケージへの完全パスを示すコマンドを使うことです。また、 `PathToTarget` ファイルを抽出するフォルダーのフルパスを表します。

## <a name="running-the-tool"></a>ツールを実行する

1) Microsoft Teams 室のデバイスで管理者アカウントにサインインして、管理者特権のコマンドプロンプトを起動します。
2) Microsoft teams 室のインストールパッケージから抽出されたファイルに含まれている、Microsoft Teams の会議室のデバイスで確認することができ `RecoveryTool.ps1 file` ます。 キットは、前提条件を準備するときに使用したネットワーク共有または USB ドライブにあります。
3) 実行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` します。
4) 出荷時の復元を実行するには:
   1. スクリプトによってプロンプトが表示されたら、[オプション 2: **リセット**] を選びます。
   2. BitLocker がオンになっている場合は、スクリプト出力の最後に示されている手順に従って、無効にします。
   3. 出荷時の復元を実行します。
      1. **設定**アプリを開き、[**更新] &** の [セキュリティ] を選択します。
      2. [ **回復** ] タブに移動します。
      3. [**この PC をリセット**する] の下で、[**はじめ**に] を選択します。
      4. [**すべて削除**]、[**次へ**]、[**リセット**] の順に選択します。
        > [!WARNING]
        > Microsoft Teams の会議室のデバイスは、 **[自分のファイルを保持する] でアプリと設定を削除** した場合、使用できなくなる可能性がありますが、Windows のリセットプロセス中に個人用のファイルオプションが選択されたままになります。 このオプションは選択しないでください。
      5. システムが複数回再起動します。 リセットが完了すると、Windows の「box で動作しません」 (OOBE) 画面にシステムが表示されます。



## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
