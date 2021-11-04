---
title: デバイス更新
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft は、サーバーにインポートしてユーザーに配布できる Skype for Business 電話 Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースします。 最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページに移動し、Phone Edition を検索します。最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後、Import-CsDeviceUpdate コマンドレットを使用して、抽出された .CAB ファイルにあるデバイス更新ルール (名前は UCUpdates.cab) をインポートできます。 詳細については、「Import-CsDeviceUpdate」を参照してください。
ms.openlocfilehash: 8758473504ebc7707d79f9fab3d2d4b60c0670ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772493"
---
# <a name="device-update"></a>デバイス更新

Microsoft は、サーバーにインポートしてユーザーに配布できる Skype for Business 電話 Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースします。 最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページに移動し、"電話 Edition" を検索します。 最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後 **、Import-CsDeviceUpdate** コマンドレットを使用して、抽出された .CAB ファイル (名前が UCUpdates.cab) にあるデバイス更新ルールをインポートできます。 詳細については [、「Import-CsDeviceUpdate」を参照してください](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

デバイス更新ルールをインポートした後、[デバイスの更新]ページを使用して、組織のデバイスのこれらのルールを表示および管理できます。

> [!TIP]
> ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイスの更新**] ページでは次のタスクを実行できます。

- 一覧のデバイス更新を承認する。

- 保留中のデバイス更新を取り消したり、元に戻したりする。

- 一覧からデバイス更新を削除する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **編集** このオプションを使用すると、次の操作を実行できます。

  - **[すべて選択]** このオプションは、リスト内のすべてのデバイス更新プログラムを選択します。

  - **削除** このオプションは、選択したデバイスの更新プログラムをすべて削除します。

- **アクション** 一覧で 1 つ以上の更新プログラムを選択し、次の操作を実行できます。

  - **保留中の更新プログラムのキャンセル** このオプションを使用すると、選択した更新プログラムが組織のデバイスに展開されません。

  - **承認** このオプションを使用すると、選択した更新プログラムを組織のデバイスに展開できます。

  - **復元** このオプションを使用すると、以前に承認された更新プログラムを組織のデバイスに展開できます。

- **更新** リストを更新して、すべてのデバイス更新プログラムの状態を確認できます。

デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)」を参照してください。
## <a name="see-also"></a>関連項目

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)