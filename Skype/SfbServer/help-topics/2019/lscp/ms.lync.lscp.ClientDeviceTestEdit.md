---
title: Test Device Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: テスト デバイス機能はデバイス更新機能と連携して動作します。 [テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロール パネルの [テスト デバイス] ページの一覧にデバイスが表示されます。
ms.openlocfilehash: e1a8c570714b1096d14ac49260922c1a6dc3fecc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830327"
---
# <a name="test-device-create-new-or-edit-existing"></a>テスト デバイス: 新規作成または現在の形式のままで編集

テスト デバイス機能はデバイス更新機能と連携して動作します。 [**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロールパネルの [テスト デバイス] ページの一覧にデバイスが表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 テスト デバイス**] または [**編集 テスト デバイス**] ページでは、次のタスクを実行できます。

- 新しいテスト デバイスを追加する。

- 既存のテスト デバイスのプロパティを変更する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **スコープ** テスト デバイスのスコープ (グローバルまたはサイト) を識別します。

- **名前** テスト デバイスの名前を追加または変更できます。

- **デバイス名** テスト デバイスの名前を追加または変更できます。

- **識別子の種類** 次のいずれかを選択して、デバイスの識別に使用する方法を選択できます。

  - **MAC アドレス**

  - **シリアル番号**

- **一意識別子** デバイスの MAC アドレスまたはシリアル番号を入力できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
