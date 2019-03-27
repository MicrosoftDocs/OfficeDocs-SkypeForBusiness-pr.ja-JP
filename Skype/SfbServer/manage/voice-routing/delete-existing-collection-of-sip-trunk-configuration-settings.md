---
title: ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。 '
ms.openlocfilehash: 6a7c90bf7ff435b0936b34bc57d391e06093040a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879365"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。

SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。 たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件です。
- かどうか各トランクには、セキュリティで保護されたリアルタイム プロトコル (SRTP) 暗号化が必要です。

ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、グローバル コレクション内のプロパティを既定値に「リセット」に、Skype ビジネス ServerControl パネルの[削除 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットを使用できます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。

管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。

- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
- サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。

**ビジネス サーバーのコントロール パネルの Skype でのトランク構成の設定を削除するのには** 

1. [ビジネス サーバーのコントロール パネルの Skype、**音声ルーティング**を**トランク構成**] をクリックします。
2. [**トランク構成**] タブで、削除、**編集**] をクリックし、[**削除**] をクリックして、SIP トランク構成設定のコレクションを選択します。 同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。
3. コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
5. **Skype ビジネス サーバーのコントロール パネル**] ダイアログ ボックスで [ **OK**] をクリックします。
6. 変わったし、コレクションを削除しないことを決定するは、**コミット**をクリックし、**すべてのコミットされていない変更をキャンセル**] をクリックします。 **Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスが表示されたら、[ **OK**] をクリックします。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してトランク構成設定を削除します。


トランク構成設定を削除するには、Windows PowerShell と**削除 CsTrunkConfiguration**コマンドレットを使用しています。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 

**指定した設定のコレクションを削除するには**

次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**サイト スコープに適用されているすべてのコレクションを削除するには**

次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**メディア バイパスが有効になっているすべてのコレクションを削除するには**

次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

詳細については、[削除 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットのヘルプ トピックを参照してください。
