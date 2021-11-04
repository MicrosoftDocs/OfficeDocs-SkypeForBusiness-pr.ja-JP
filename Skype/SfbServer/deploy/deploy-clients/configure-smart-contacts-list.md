---
title: クライアントでスマート連絡先リストをSkype for Businessする
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: クライアントでスマート連絡先リスト機能を有効にするSkype for Businessします。'
ms.openlocfilehash: f70ffcd6893c361262c0f0f8e712d7dd0db247e7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775857"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>クライアントでスマート連絡先リストをSkype for Businessする

**概要:** クライアントでスマート連絡先リスト機能を有効にするSkype for Businessします。

スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストの自動作成が可能です。 ユーザーが最初にSkype for Businessすると、ユーザーは自分のマネージャーや他のユーザーをチームに自動的に表示します。 この機能は、Microsoft 365 および Office 365 ユーザーに対して既定で有効になっていますが、クライアント ポリシー設定を構成して、オンプレミスユーザーに対してこの機能を明示的に有効にする必要があります。

この機能を構成する場合は、次の注意が必要です。

- 最大 13 人のユーザーは、次の順序でスマート連絡先リストに自動的に追加されます。

  1. Manager

  2. アルファベット順に指示する

  3. アルファベット順のピア

- ユーザーが初めてログインすると、My Group という名前の新しいグループが作成されます。 グループには、[マネージャー] フィールドに入力されたユーザー エイリアスに基ADユーザーのグループ関係のユーザーが自動的に設定されます。 グループ メンバーシップに対する変更AD、最初に設定した後にマイ グループを更新する場合は発生し得ない点に注意してください。 ユーザーが連絡先またはグループを削除した場合、連絡先もグループも再作成されません。 

- 自動タグ付けをオンにすると、リスト内の連絡先にプレゼンスの変更のタグが付けされます。 自動タグ付けは既定でオンになっていますが、無効にできます。 

- グループ内のすべての新しいユーザーに、連絡先リストに追加されたという通知が表示されます。 ユーザーは、自分のマイ グループまたは選択した他のグループに新しいメンバーを手動で追加できます。

- この機能は、初めてサインインするユーザーにのみ機能します。 ユーザーが以前に任意のデバイスからサインインしている場合 (たとえば、モバイル デバイスや Mac など) は、そのユーザーに対して有効になっていません。

## <a name="configure-smart-contacts-list"></a>スマート連絡先リストの構成

ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。 

- 新しい CsClientPolicy エントリを作成し、グローバル クライアント ポリシーに追加します。 

- アドレス帳検索が Web 検索専用に構成されていることを確認します。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>スマート連絡先リストを有効にするポリシー エントリを作成する

スマート連絡先リスト機能を有効にするポリシー エントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを使用して [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) コマンドレットを使用します。

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

次に [、Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットを使用して、次のようにグローバル ポリシーに変更を書き込みます。

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要があります。 詳細については [、「Set-CsClientPolicy」を参照してください](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>トラブルシューティング

スマート連絡先リストが期待通り機能していない場合は、次の項目を確認します。

- 構成を検証します。 

- 組織の情報がAD確認します。

- 新Skype for Businessのクライアント ログを収集して、詳細な分析を行います。

- クライアント UI Skype for Businessアドレス帳に接続できないというメッセージが表示されていないか確認します。 アドレス帳の接続を確認するには、クライアント検索バーでユーザー Skype for Business実行します。

- AD DS レプリケーションの問題により、ユーザーが最初にサインインした際に連絡先が解決Skype for Business。