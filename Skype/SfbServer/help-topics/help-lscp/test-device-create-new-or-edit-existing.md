---
title: デバイスの新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: テスト デバイス機能はデバイス更新機能と連携して動作します。 [テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [テストデバイス] ページの一覧に表示されます。
ms.openlocfilehash: 56f5c7b43f55f50c5fa5e73cade3f74bea752778
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699468"
---
# <a name="test-device-create-new-or-edit-existing"></a>テスト デバイス: 新規作成または現在の形式のままで編集

テスト デバイス機能はデバイス更新機能と連携して動作します。 [**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 テスト デバイス**] または [**編集 テスト デバイス**] ページでは、次のタスクを実行できます。

- 新しいテスト デバイスを追加する。

- 既存のテスト デバイスのプロパティを変更する。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **スコープ**テストデバイスのスコープ (グローバルまたはサイト) を識別します。

- **名前**テストデバイスの名前を追加または変更することができます。

- **デバイス名**テストデバイスの名前を追加または変更することができます。

- **識別子の種類**以下のいずれかを選択して、デバイスの識別に使用する方法を選ぶことができます。

  - **MAC アドレス**

  - **シリアル番号**

- **一意の識別子**デバイスの MAC アドレスまたはシリアル番号を入力できます。

デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)」を参照してください。
## <a name="see-also"></a>関連項目

[テスト デバイス](test-device.md)

[新規-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[組織内のデバイスのソフトウェア更新プログラムを表示する](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
