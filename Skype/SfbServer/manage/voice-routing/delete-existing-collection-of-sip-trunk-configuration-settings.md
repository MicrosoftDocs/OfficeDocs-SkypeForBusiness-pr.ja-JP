---
title: Skype for Business Server の SIP トランク構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。 '
ms.openlocfilehash: c24633e598efe8f5bd9f62e7e46651045d24b71b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120899"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server の SIP トランク構成設定の既存のコレクションを削除する

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- Real-time Transport Control Protocol (RTCP) パケットが送信される条件。
- 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、Skype for Business ServerControl Panel または [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) コマンドレットを使用して、グローバル コレクションのプロパティを既定値に "リセット" できます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。

管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。

- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
- サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。

**Skype for Business Server コントロール パネルを使用してトランク構成設定を削除するには** 

1. Skype for Business Server コントロールパネルで、[音声ルーティング] をクリックし、[トランク構成]**をクリックします**。
2. [トランク **構成] タブで**、削除する SIP トランク構成設定のコレクションを選択し、[編集] をクリックし、[削除] を **クリックします**。 同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。
3. コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
5. [Skype **for Business Server コントロール パネル] ダイアログ ボックスで****、[OK] をクリックします**。
6. 変更してコレクションを削除しない場合は、[コミット] をクリックし、[すべてのコミットされていない変更を取り消す]**をクリックします**。 [Skype **for Business Server コントロール パネル] ダイアログ ボックスが** 表示されたら **、[OK] をクリックします**。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したトランク構成Windows PowerShell削除する


トランク構成設定を削除するには、Windows PowerShell **Remove-CsTrunkConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 

**指定した設定のコレクションを削除するには**

次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**サイト スコープに適用されているコレクションを削除するには**

次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**メディア バイパスが有効になっているすべてのコレクションを削除するには**

次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

詳細については [、Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。