---
title: デバイス更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft は、Skype for Business Phone Edition 用の新しいデバイスファームウェア更新プログラムセットを定期的にリリースします。これにより、サーバーにインポートして、ユーザーに配布することができます。 最新のデバイス更新ルールを取得するには、Microsoft web サイトの [ヘルプとサポート] ページに移動して、[電話] エディションを検索します。最新の更新プログラムパッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後、インポート-CsDeviceUpdate コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル ("UCUpdates .cab" という名前が付いています)。 詳細については、「CsDeviceUpdate のインポート」を参照してください。
ms.openlocfilehash: 066564a315fdda57e33ad62f8abfe8e5dbe931e1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700242"
---
# <a name="device-update"></a>デバイスの更新

Microsoft は、Skype for Business Phone Edition 用の新しいデバイスファームウェア更新プログラムセットを定期的にリリースします。これにより、サーバーにインポートして、ユーザーに配布することができます。 最新のデバイス更新ルールを取得するには、Microsoft web サイトの [ヘルプとサポート] ページにアクセスし、"Phone Edition" を検索します。 最新の更新プログラムパッケージをダウンロードして、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後、**インポート-CsDeviceUpdate**コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル ("UCUpdates .cab" という名前が付いています)。 詳細については、「 [CsDeviceUpdate のインポート](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)」を参照してください。

デバイス更新ルールをインポートした後、[**デバイス更新**] ページを使用して、組織のデバイスのこれらのルールを表示および管理できます。

> [!TIP]
> ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**デバイスの更新**] ページでは次のタスクを実行できます。

- 一覧のデバイス更新を承認する。

- 保留中のデバイス更新を取り消したり、元に戻したりする。

- 一覧からデバイス更新を削除する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **編集**このオプションを使うと、次の操作を実行できます。

  - **すべて選択**このオプションでは、一覧にあるすべてのデバイスの更新が選択されます。

  - **削除**このオプションでは、選択したすべてのデバイスの更新を削除します。

- **操作**リストで1つまたは複数の更新を選択して、次の操作を実行できます。

  - **保留中の更新をキャンセル**するこのオプションでは、選択した更新プログラムが組織のデバイスに展開されないようにします。

  - **承認**このオプションでは、選択した更新プログラムを組織のデバイスに展開することができます。

  - **復元**このオプションでは、以前に承認された更新を組織のデバイスに展開することができます。

- **更新**リストを更新して、すべてのデバイスの更新の状態を確認できます。

デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[インポート-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
