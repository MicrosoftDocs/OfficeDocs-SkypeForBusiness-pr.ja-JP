---
title: テスト デバイス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [テストデバイス] ページの一覧に表示されます。'
ms.openlocfilehash: ea6d0e74bf72a8887b3c6cd0f9c46e503af316fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822049"
---
# <a name="test-device"></a>テスト デバイス

[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

**テストデバイス**ページでは、次のタスクを実行できます。

- テストデバイスをグローバルに、または特定のサイトに追加します。

- 既存のテストデバイスのオプションを変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **新規**次のスコープを使用して、新しいテストデバイスを追加できます。

  - グローバル

  - サイト

- **編集**リスト内のテストデバイスのオプションを変更できます。 このオプションを使うと、次の操作を行うことができます。

  - **詳細を表示**このオプションを選択すると、テストデバイスのオプションを変更できるダイアログボックスが表示されます。

  - **すべて選択**このオプションでは、リスト内のすべてのテストデバイスを選択します。

  - **削除**このオプションでは、選択したすべてのテストデバイスを削除します。

- **更新**テストデバイスの一覧を更新して、すべてのテストデバイスのオプションの状態を確認できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス: 新規作成または現在の形式のままで編集](test-device-create-new-or-edit-existing.md)

[新規-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
