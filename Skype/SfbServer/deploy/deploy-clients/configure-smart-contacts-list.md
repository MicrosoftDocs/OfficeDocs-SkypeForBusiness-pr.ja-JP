---
title: Skype for Business クライアントでスマート連絡先リストを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768870"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Skype for Business クライアントでスマート連絡先リストを構成する

**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。

スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストを自動的に設定できます。 初めて Skype for Business を使用すると、ユーザーは自分の上司と自分のチームメンバーを自動的に確認できます。 Office 365 ユーザーの場合、この機能は既定でオンになっていますが、クライアントポリシーの設定を構成することで、オンプレミスのユーザーに対してこの機能を明示的に有効にする必要があります。

この機能を構成する場合は、次の点に注意してください。

- 最大13人のユーザーは、次の順序でスマート連絡先リストに自動的に追加されます。

  1. 上司

  2. 直属の上司 (アルファベット順)

  3. 同僚 (アルファベット順)

- ユーザーの最初のログイン時に、[マイ グループ] という名前の新しいグループが作成されます。 このグループには、[管理者] フィールドに入力されたユーザーエイリアスに基づいて、ユーザーの AD グループの関係に含まれるユーザーが自動的に設定されます。 AD グループ メンバーシップを変更しても、最初に設定された [マイ グループ] は更新されません。 連絡先やグループを削除すると、その連絡先やグループが再作成されることはありません。 

- 自動タグ付けが有効の場合、リスト内の連絡先がプレゼンスの変更に応じてタグ付けされます。 自動タグ付けは既定で有効ですが、無効にすることもできます。 

- グループ内のすべての新規ユーザーに対して、自分が連絡先リストに追加されたことが通知されます。 ユーザーは新しいメンバーを、[マイ グループ] や任意の他のグループに手動で追加できます。

- この機能はユーザーの初回ログイン時にのみ適用されます。 他のデバイス (モバイル デバイスや Mac など) から以前にログインしたことがあるユーザーに対しては、この機能は有効になりません。

## <a name="configure-smart-contacts-list"></a>スマート連絡先リストを構成する

ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。 

- 新しい CsClientPolicy エントリを作成して、グローバルクライアントポリシーに追加します。 

- [アドレス帳の検索] が [Web 検索] のみに構成されていることを確認します。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>ポリシー エントリを作成してスマート連絡先リストを有効にする

スマート連絡先リスト機能を有効にするポリシーエントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを使用して、[新しい-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用します。

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

次に、次の[手順でグローバル](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)ポリシーへの変更を書き込みます。

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。 詳細については、「 [CsClientPolicy を設定](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)する」を参照してください。 

### <a name="troubleshoot"></a>トラブルシューティング

スマート連絡先リストが正しく機能しない場合は、次のことを確認してください。

- 構成を検証します。 

- AD 組織情報が設定されていることを確認します。

- さらに詳しく分析するには、新しいユーザーに Skype for Business クライアントログを収集します。

- Skype for Business クライアントの UI に、アドレス帳に接続できないことを示すメッセージが表示されていないことを確認します。 アドレス帳の接続を確認するには、Skype for Business クライアントの検索バーでユーザーを検索します。

- AD DS のレプリケーションの問題により、ユーザーが最初に Skype for Business にサインインしたときに連絡先が未解決になることがあります。


