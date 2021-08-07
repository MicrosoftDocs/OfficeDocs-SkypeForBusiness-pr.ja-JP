---
title: 'Skype for Business Server: SIP トランク構成設定の既存のコレクションを削除する'
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
description: '概要: [コントロール パネル] を使用してトランク構成設定のコレクションを削除するSkype for Business Server説明します。'
ms.openlocfilehash: 294a6c2e39387aa9245af0c23eec56d1fd59dbc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772868"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server: SIP トランク構成設定の既存のコレクションを削除する 
 
**概要:**[コントロール パネル] を使用してトランク構成設定のコレクションを削除するSkype for Business Server説明します。
  
SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP-Public ブランチ eXchange (PBX)、またはサービス プロバイダーのセッション ボーダー コントローラー (SBC) との間の関係と機能を定義します。 たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効にする必要があるかどうか
    
- リアルタイム トランスポート制御プロトコル (RTCP) パケットが送信される条件
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化が必要かどうか
    
サーバーをインストールSkype for Business Server、SIP トランク構成設定のグローバル コレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、Skype for Business Server コントロール パネルまたは[Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration)コマンドレットを使用して、グローバル コレクションのプロパティを既定値に "リセット" できます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。
  
管理者は、サイト スコープまたはサービス スコープ (個々の PSTN ゲートウェイ用) でカスタム トランク構成設定を作成することもできます。これらのカスタム設定は削除できます。 これらのカスタム設定を削除する場合は、次のことを念頭に置きます。
  
- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
    
- サイトスコープの設定を削除すると、これらの設定によって管理される SIP トランクは、トランク構成設定のグローバル コレクションによって管理されます。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用してトランク構成Skype for Business Server削除するには

1. [コントロール Skype for Business Server] で、[音声ルーティング]**を** クリックし、[トランク構成]**をクリックします**。
    
2. [トランク **構成] タブで**、削除する SIP トランク構成設定のコレクションを選択し、[編集] をクリックし、[削除] を **クリックします**。 同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら削除する他のコレクションをクリックします。
    
3. コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。
    
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
    
5. [コントロール **Skype for Business Server] ダイアログ ボックスで****、[OK] をクリックします**。
    
6. 後でコレクションを削除しないことにした場合は、[**コミット**]、[**コミットされていないすべての変更を取り消し**] の順にクリックします。 [コントロール **Skype for Business Server] ダイアログ ボックスが** 表示されたら **、[OK] をクリックします**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>管理シェル コマンドレットを設定によるトランクSkype for Business Serverの削除

トランク構成設定を削除するには、管理シェルSkype for Business Server **Remove-CsTrunkConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server管理シェルから、または管理シェルのリモート セッションSkype for Business Server実行できます。
  
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

詳細については [、Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) コマンドレットのヘルプ トピックを参照してください。
