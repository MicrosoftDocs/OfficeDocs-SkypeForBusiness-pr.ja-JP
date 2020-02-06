---
title: Skype for Business Server で既存の SIP トランク構成設定のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 '
ms.openlocfilehash: 5be81bccdb5df94cff4e8a2a13aaabb20dfdce29
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816977"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で既存の SIP トランク構成設定のコレクションを削除する

SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。
- 各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、Skype for Business ServerControl Panel または[set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットを使用して、グローバルコレクションのプロパティを既定値に "リセット" することができます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。

管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。

- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
- サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。

**Skype for Business Server コントロールパネルでトランク構成設定を削除するには** 

1. Skype for Business Server コントロールパネルで、[**音声ルーティング**] をクリックし、[ **Trunk 構成**] をクリックします。
2. [**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**] をクリックして、[**削除**] をクリックします。 同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。
3. コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
5. [ **Skype For Business Server コントロールパネル**] ダイアログボックスで、[ **OK**] をクリックします。
6. コレクションを削除しないようにする場合は、[**コミット**] をクリックし、[コミットされていない**変更をすべてキャンセル**] をクリックします。 [ **Skype For Business Server コントロールパネル**] ダイアログボックスが表示されたら、[ **OK**] をクリックします。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したトランク構成設定の削除


Windows PowerShell と**set-cstrunkconfiguration**コマンドレットを使用して、トランク構成設定を削除できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 

**指定した設定のコレクションを削除するには**

次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**サイト スコープに適用されているすべてのコレクションを削除するには**

次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**メディア バイパスが有効になっているすべてのコレクションを削除するには**

次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

詳細については、 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットのヘルプトピックを参照してください。
