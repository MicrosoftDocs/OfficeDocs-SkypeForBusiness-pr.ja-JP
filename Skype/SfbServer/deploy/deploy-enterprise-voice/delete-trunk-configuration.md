---
title: Skype for Business Server の SIP トランク構成設定の既存のコレクションを削除する
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '概要: Skype for Business Server コントロール パネルを使用してトランク構成設定のコレクションを削除する方法について説明します。'
ms.openlocfilehash: 8ea3ef931c8e09a235adc816cd993468d7d79b47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111853"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server の SIP トランク構成設定の既存のコレクションを削除する
 
**概要:** Skype for Business Server コントロール パネルを使用してトランク構成設定のコレクションを削除する方法について説明します。
  
SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP-Public ブランチ eXchange (PBX)、またはサービス プロバイダーのセッション ボーダー コントローラー (SBC) との間の関係と機能を定義します。 たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効化するか。
    
- リアルタイム トランスポート制御プロトコル (RTCP) パケットが送信される条件。
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化が必要かどうか。
    
Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、Skype for Business Server コントロール パネルまたは [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) コマンドレットを使用して、グローバル コレクションのプロパティを既定値に "リセット" できます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。
  
管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。
  
- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
    
- サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してトランク構成設定を削除するには

1. Skype for Business Server コントロール パネルで、[音声ルーティング] **をクリック** し、[トランク構成] **をクリックします**。
    
2. [**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**]、[**削除**] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。
    
3. コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。
    
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
    
5. [Skype **for Business Server コントロール パネル] ダイアログ ボックスで****、[OK] をクリックします**。
    
6. 後でコレクションを削除しないことにした場合は、[**コミット**]、[**コミットされていないすべての変更を取り消し**] の順にクリックします。 [Skype **for Business Server コントロール パネル] ダイアログ ボックスが** 表示されたら **、[OK] をクリックします**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Management Shell コマンドレットを使用したトランク構成設定の削除

トランク構成設定は、Skype for Business Server 管理シェルと **Remove-CsTrunkConfiguration** コマンドレットを使用して削除できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Skype for Business Server 管理シェルのリモート セッションから実行できます。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>指定した設定のコレクションを削除するには

- 次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>サイト スコープに適用されているコレクションを削除するには

- 次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>メディア バイパスが有効になっているすべてのコレクションを削除するには

- 次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

詳細については [、Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
