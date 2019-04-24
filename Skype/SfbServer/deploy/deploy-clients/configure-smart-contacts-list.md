---
title: ビジネス クライアント用の Skype でスマート アドレス帳を構成します。
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: ビジネス クライアント用の Skype でスマートの連絡先リストの機能を有効にする方法を説明します。'
ms.openlocfilehash: 52de1eb889b1373dc6928c90a9e0e298f467d3fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212776"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>ビジネス クライアント用の Skype でスマート アドレス帳を構成します。

**の概要:** ビジネス クライアント用の Skype でスマートの連絡先リストの機能を有効にする方法を説明します。

スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストを自動的に設定できます。 最初に、ユーザーは、ビジネスの Skype を使用すると、自動的に参照してくださいそのマネージャーと他の人の中で。 Office 365 ユーザーは、既定でこの機能が有効になっているが、クライアントのポリシー設定を構成することにより、オンプレミス ユーザーのこの機能を有効する必要があります明示的にします。

この機能を構成する場合は、次の点に注意してください。

- 13、最大のユーザーは、次の順序で、スマート アドレス帳に自動的に追加されます。

  1. 上司

  2. 直属の上司 (アルファベット順)

  3. 同僚 (アルファベット順)

- ユーザーの最初のログイン時に、[マイ グループ] という名前の新しいグループが作成されます。 グループは、[管理者] フィールドに入力するユーザーのエイリアスに基づいてユーザーの AD グループの関係の人が表示されます。 AD グループ メンバーシップを変更しても、最初に設定された [マイ グループ] は更新されません。 連絡先やグループを削除すると、その連絡先やグループが再作成されることはありません。 

- 自動タグ付けが有効の場合、リスト内の連絡先がプレゼンスの変更に応じてタグ付けされます。 自動タグ付けは既定で有効ですが、無効にすることもできます。 

- グループ内のすべての新規ユーザーに対して、自分が連絡先リストに追加されたことが通知されます。 ユーザーは新しいメンバーを、[マイ グループ] や任意の他のグループに手動で追加できます。

- この機能はユーザーの初回ログイン時にのみ適用されます。 他のデバイス (モバイル デバイスや Mac など) から以前にログインしたことがあるユーザーに対しては、この機能は有効になりません。

## <a name="configure-smart-contacts-list"></a>スマート連絡先リストを構成する

ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。 

- CsClientPolicy の新しいエントリを作成し、グローバル クライアント ポリシーに追加します。 

- [アドレス帳の検索] が [Web 検索] のみに構成されていることを確認します。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>ポリシー エントリを作成してスマート連絡先リストを有効にする

スマート連絡先リスト機能を有効にするには、次のように EnableClientAutoPopulateWithTeam オプションを使用して[新規 CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用してポリシー エントリを作成します。

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

次に、次のように、グローバル ポリシーに変更を記述するのに[セット CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットを使用します。

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。 詳細については、[一連の CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)を参照してください。 

### <a name="troubleshoot"></a>トラブルシューティング

スマート連絡先リストが正しく機能しない場合は、次のことを確認してください。

- 構成を検証します。 

- AD 組織情報が設定されていることを確認します。

- ビジネス クライアントのログの詳細な分析の新しいユーザーの Skype を収集します。

- ビジネス クライアント UI の Skype では、アドレス帳に接続できないというメッセージが表示されないことを確認します。 接続のアドレス帳を削除するには、ビジネスのクライアントの検索バーの Skype のユーザーの検索を実行します。

- AD DS レプリケーションの問題には、連絡先とユーザー最初にサインインしているビジネスの Skype が解決されていない可能性があります。


