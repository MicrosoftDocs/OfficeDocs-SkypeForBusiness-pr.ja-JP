---
title: テスト デバイス
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、デバイスが [デバイスのテスト] ページの一覧に表示され、Skype for Business Serverされます。'
ms.openlocfilehash: aaac51fa7124436b6253f88a33d36758d2cb061c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834645"
---
# <a name="test-device"></a>テスト デバイス

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、コントロール パネルの [テスト デバイス] ページの一覧にSkype for Business Serverされます。

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

[テスト デバイス: 新規作成または現在の形式のままで編集](ms.lync.lscp.ClientDeviceTestEdit.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)