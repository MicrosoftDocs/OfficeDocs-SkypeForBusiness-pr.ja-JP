---
title: Skype for Business クライアントでのスマート連絡先リストの構成
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
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776692"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Skype for Business クライアントでのスマート連絡先リストの構成

**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。

スマート連絡先リスト機能を使用すると、エンドユーザーに対して連絡先リストを自動的に作成できます。 最初に Skype for Business を使用すると、ユーザーは自分のチームの上司とその他の人を自動的に確認できます。 この機能は、Microsoft 365 および Office 365 ユーザーに対しては既定で有効になっていますが、クライアントポリシー設定を構成して、オンプレミスユーザーに対してこの機能を明示的に有効にする必要があります。

この機能を構成する場合は、次の点に注意してください。

- 最大13人のユーザーが自動的にスマート連絡先リストに追加されます。

  1. Manager

  2. アルファベット順での指示

  3. ピア (アルファベット順)

- ユーザーが最初にログインしたときに、"My Group" という名前の新しいグループが作成されます。 このグループには、[管理者] フィールドに設定されたユーザーエイリアスに基づいて、ユーザーの AD グループの関係にあるユーザーが自動的に設定されます。 AD グループのメンバーシップに対する変更では、最初に設定された後に、グループの更新が発生しないことに注意してください。 ユーザーが連絡先またはグループを削除した場合、連絡先またはグループは再作成されません。 

- 自動タグ付けが有効になっている場合は、リスト内の連絡先にプレゼンスの変更がタグ付けされます。 自動タグ付けは既定で有効になっていますが、オフにすることもできます。 

- グループ内のすべての新しいユーザーに、連絡先リストに追加されたことが通知されます。 ユーザーは、自分のグループまたはその他のグループに新しいメンバーを手動で追加することができます。

- この機能は、初めてサインインしているユーザーに対してのみ有効です。 ユーザーが、モバイルデバイスや Mac などのすべてのデバイスから以前にサインインしていた場合は、そのユーザーに対して機能が有効になっていないことを示します。

## <a name="configure-smart-contacts-list"></a>スマート連絡先リストの構成

ユーザーに対してスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。 

- 新しい CsClientPolicy エントリを作成し、それをグローバルクライアントポリシーに追加します。 

- アドレス帳検索が Web 検索専用に構成されていることを確認します。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>スマート連絡先リストを有効にするポリシーエントリを作成する

スマート連絡先リスト機能を有効にするポリシーエントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを指定して、[新しい-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用します。

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

次に、次のように、 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットを使用して、グローバルポリシーに対する変更を書き込みます。

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

オプションで、自動タグ付けをオフにするポリシーを次のように作成することもできます。

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。 詳細については、「 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)」を参照してください。 

### <a name="troubleshoot"></a>トラブルシューティング

スマート連絡先リストが期待どおりに機能しない場合は、次の点を確認してください。

- 構成を検証します。 

- AD 組織の情報が入力されていることを確認します。

- 詳細な分析を行うために、新しいユーザーの Skype for Business クライアントログを収集します。

- Skype for Business クライアントの UI に、アドレス帳に接続できないことを示すメッセージが表示されないことを確認します。 アドレス帳の接続を確認するには、Skype for Business クライアント検索バーでユーザーの検索を実行します。

- ユーザーが Skype for Business に初めてサインインすると、AD DS のレプリケーションの問題によって連絡先が未解決になることがあります。


