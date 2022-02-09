---
title: Test Device Create New or Edit Existing
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: テスト デバイス機能はデバイス更新機能と連携して動作します。 [テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、デバイスが [デバイスのテスト] ページの一覧に表示され、Skype for Business Serverされます。
ms.openlocfilehash: 340dc4d412f38d5d92a494a1b247d81ea650ae95
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400651"
---
# <a name="test-device-create-new-or-edit-existing"></a>テスト デバイス: 新規作成または現在の形式のままで編集

テスト デバイス機能はデバイス更新機能と連携して動作します。 [**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、デバイスが [デバイスのテスト] ページの一覧に表示され、Skype for Business Serverされます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 テスト デバイス**] または [**編集 テスト デバイス**] ページでは、次のタスクを実行できます。

- 新しいテスト デバイスを追加する。

- 既存のテスト デバイスのプロパティを変更する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **スコープ** テスト デバイスのスコープ (グローバルまたはサイト) を識別します。

- **名前** テスト デバイスの名前を追加または変更できます。

- **デバイス名** テスト デバイスの名前を追加または変更できます。

- **識別子の種類** デバイスの識別に使用する方法を選択するには、次のいずれかを選択します。

  - **MAC アドレス**

  - **シリアル番号**

- **一意識別子** デバイスの MAC アドレスまたはシリアル番号を入力できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)