---
title: Skype for Business クライアントでスマート連絡先リストを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について学習します。'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805777"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Skype for Business クライアントでスマート連絡先リストを構成する

**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について学習します。

スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストを自動的に作成できます。 最初に Skype for Business を使用すると、ユーザーには自分のマネージャーとチームの他のユーザーが自動的に表示されます。 この機能は、Microsoft 365 および Office 365 ユーザーに対して既定で有効になっていますが、クライアント ポリシー設定を構成して、オンプレミス ユーザーに対してこの機能を明示的に有効にする必要があります。

この機能を構成する場合は、次の注意が必要です。

- 最大 13 人のユーザーは、次の順序でスマート連絡先リストに自動的に追加されます。

  1. Manager

  2. Directs をアルファベット順に並べ替え

  3. ピア (アルファベット順)

- ユーザーが初めてログインすると、My Group という名前の新しいグループが作成されます。 グループには、マネージャー フィールドに入力されたユーザー エイリアスに基ADユーザーのグループ関係のユーザーが自動的に設定されます。 グループ メンバーシップを変更AD、最初に設定した後にグループが更新されるのではない点に注意してください。 ユーザーが連絡先またはグループを削除した場合、連絡先もグループも再作成されません。 

- 自動タグ付けが有効になっている場合、リスト内の連絡先にはプレゼンスの変更のタグが付けされます。 自動タグ付けは既定で有効になっていますが、無効にできます。 

- グループ内のすべての新しいユーザーには、連絡先リストに追加されたという通知が表示されます。 ユーザーは、自分のマイ グループまたは選択した他のグループに新しいメンバーを手動で追加できます。

- この機能は、初めてサインインするユーザーにのみ機能します。 ユーザーが以前に任意のデバイス (モバイル デバイスや Mac など) からサインインした場合、そのユーザーに対してこの機能は有効になりません。

## <a name="configure-smart-contacts-list"></a>スマート連絡先リストの構成

ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。 

- 新しい CsClientPolicy エントリを作成し、グローバル クライアント ポリシーに追加します。 

- アドレス帳検索が Web 検索専用に構成されていることを確認します。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>スマート連絡先リストを有効にするポリシー エントリを作成する

スマート連絡先リスト機能を有効にするポリシー エントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを指定して [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) コマンドレットを使用します。

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

次に [、Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットを使用して、次のようにグローバル ポリシーに変更を書き込みます。

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要があります。 詳細については [、「Set-CsClientPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>トラブルシューティング

スマート連絡先リストが期待通り機能しない場合は、次の項目を確認します。

- 構成を検証します。 

- 組織の情報AD入力します。

- 新しいユーザーの Skype for Business クライアント ログを収集して、さらに分析します。

- Skype for Business クライアント UI にアドレス帳に接続できないことを示すメッセージが表示されていないのを確認します。 アドレス帳の接続を確認するには、Skype for Business クライアント検索バーでユーザーの検索を実行します。

- AD DS レプリケーションの問題が発生すると、ユーザーが初めて Skype for Business にサインインするときに連絡先が解決されません。


