---
title: デバイス更新
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft は、Skype for Business Phone Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースしています。この更新プログラムは、サーバーにインポートしてユーザーに配布できます。 最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページに移動し、Phone Edition を検索します。最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後、Import-CsDeviceUpdate コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル (名前は UCUpdates.cab)。 詳細については、「Import-CsDeviceUpdate」を参照してください。
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811057"
---
# <a name="device-update"></a>デバイス更新

Microsoft は、Skype for Business Phone Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースしています。この更新プログラムは、サーバーにインポートしてユーザーに配布できます。 最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページで「Phone Edition」を検索します。 最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後 **、Import-CsDeviceUpdate** コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル (名前は UCUpdates.cab)。 詳細については [、「Import-CsDeviceUpdate」を参照してください](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

デバイス更新ルールをインポートした後、[デバイス更新] ページを使用して、組織のデバイスに対するこれらのルールを表示および管理できます。

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

  - **すべて選択** このオプションは、一覧内のすべてのデバイス更新プログラムを選択します。

  - **削除** このオプションは、選択したデバイスの更新プログラムをすべて削除します。

- **アクション** 一覧から 1 つ以上の更新プログラムを選択し、次の操作を実行できます。

  - **保留中の更新を取り消す** このオプションを使用すると、選択した更新プログラムが組織のデバイスに展開されません。

  - **承認** このオプションを使用すると、選択した更新プログラムを組織のデバイスに展開できます。

  - **復元** このオプションを使用すると、以前に承認された更新プログラムを組織のデバイスに展開できます。

- **更新** 一覧を更新して、すべてのデバイス更新プログラムの状態を確認できます。

デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
