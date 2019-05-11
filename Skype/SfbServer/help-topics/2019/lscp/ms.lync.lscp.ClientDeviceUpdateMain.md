---
title: デバイス更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: マイクロソフトは定期的に、ビジネス電話編集用に、サーバーにインポートし、ユーザーに配布する、Skype のデバイスのファームウェアの更新プログラムの新しいセットを解放します。 最新の更新プログラム パッケージに、ヘルプとサポート] ページに、マイクロソフト web サイトに、forPhone Edition.Download を検索してデバイス更新ルールの最新のセットを取得し、更新プログラムをアップロードするは、コンピューターのフォルダーにファイルを抽出できます。 ファイルが抽出されたら、抽出したにデバイス更新ルールをインポートするインポート CsDeviceUpdate コマンドレットを使用できます。CAB ファイルの名前は UCUpdates.cab)。 詳細については、インポートの CsDeviceUpdate を参照してください。
ms.openlocfilehash: 3b39464c579d4fc8527246ef805ffd5523cface7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891846"
---
# <a name="device-update"></a>デバイスの更新

マイクロソフトは定期的に、ビジネス電話編集用に、サーバーにインポートし、ユーザーに配布する、Skype のデバイスのファームウェアの更新プログラムの新しいセットを解放します。 デバイス更新ルールの最新のセットを取得するには、ヘルプとサポート] ページに、マイクロソフト web サイトに、「電話のエディション」を検索します。 最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするは、コンピューターのフォルダーにファイルを抽出します。 ファイルが抽出されたら、抽出したにデバイス更新ルールをインポートする**インポート CsDeviceUpdate**コマンドレットを使用できます。CAB ファイルの名前は UCUpdates.cab)。 詳細については、[インポートの CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)を参照してください。

デバイス更新ルールをインポートした後は、表示して、組織のデバイスにこれらのルールを管理する**デバイスの更新**] ページを使用できます。

> [!TIP]
> ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイスの更新**] ページでは次のタスクを実行できます。

- 一覧のデバイス更新を承認する。

- 保留中のデバイス更新を取り消したり、元に戻したりする。

- 一覧からデバイス更新を削除する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **編集**このオプションを使用すると、次の操作を行います。

  - **すべてを選択**一覧にすべてのデバイスの更新プログラムを選択します。

  - **削除**このオプションは、選択したデバイスのすべての更新プログラムを削除します。

- **アクション**リストで 1 つまたは複数の更新プログラムを選択し、次の操作を実行できます。

  - **保留中の更新をキャンセル**このオプションは、選択した更新プログラムが、組織のデバイスに配備されていることを防ぎます。

  - **承認**このオプションは、組織のデバイスに配置する選択した更新プログラムを使用します。

  - **復元**このオプションにより、組織のデバイスに展開する更新プログラムが以前に許可されました。

- **更新**すべてのデバイスの更新プログラムの状態を確認するのにはリストを更新することができます。

デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[インポート-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
