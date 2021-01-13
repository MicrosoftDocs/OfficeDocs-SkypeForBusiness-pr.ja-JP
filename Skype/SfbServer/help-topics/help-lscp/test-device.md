---
title: テスト デバイス
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
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバルに (環境全体を通して) テストするか、単一のサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロール パネルの [テスト デバイス] ページの一覧にデバイスが表示されます。'
ms.openlocfilehash: fd32fafd3b334344fe90c28e130e016dfbcf5043
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819047"
---
# <a name="test-device"></a>テスト デバイス

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバルに (環境全体を通して) テストするか、単一のサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロールパネルの [テスト デバイス] ページの一覧にデバイスが表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[テスト デバイス] ページでは、次の **タスクを実行** できます。

- テスト デバイスをグローバルに、または特定のサイトに追加します。

- 既存のテスト デバイスのオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **新規** 次のスコープを持つ新しいテスト デバイスを追加できます。

  - グローバル

  - Site

- **編集** 一覧でテスト デバイスのオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションを選択すると、テスト デバイスのオプションを変更できるダイアログ ボックスが開きます。

  - **すべて選択** このオプションは、一覧内のすべてのテスト デバイスを選択します。

  - **Delete** このオプションを選択すると、選択したテスト デバイスすべてが削除されます。

- **更新** テスト デバイスの一覧を更新して、すべてのテスト デバイスのオプションの状態を確認できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス: 新規作成または現在の形式のままで編集](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
