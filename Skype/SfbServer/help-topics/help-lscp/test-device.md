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
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロール パネルの [テスト デバイス] ページの一覧にデバイスが表示されます。'
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099353"
---
# <a name="test-device"></a>テスト デバイス

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロールパネルの [テスト デバイス] ページの一覧にデバイスが表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[テスト デバイス] ページで次のタスク **を実行** できます。

- テスト デバイスをグローバルまたは特定のサイトに追加します。

- 既存のテスト デバイスのオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **New** 次のスコープを持つ新しいテスト デバイスを追加できます。

  - グローバル

  - サイト

- **編集** リスト内のテスト デバイスのオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションは、テスト デバイスのオプションを変更できるダイアログ ボックスを開きます。

  - **[すべて選択]** このオプションは、リスト内のすべてのテスト デバイスを選択します。

  - **削除** このオプションは、選択したテスト デバイスをすべて削除します。

- **更新** テスト デバイスの一覧を更新して、すべてのテスト デバイスのオプションの状態を確認できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス: 新規作成または現在の形式のままで編集](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)