---
title: ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '概要: ビジネス サーバーのコントロール パネルの Skype を使用してトランク構成設定のコレクションを削除する方法を説明します。'
ms.openlocfilehash: 8e960e72b6ac29e12e1cf220978f5c8b44c2691f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892791"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。
 
**の概要:** ビジネス サーバーのコントロール パネルの Skype を使用してトランク構成設定のコレクションを削除する方法について説明します。
  
SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch eXchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係と機能を定義します。たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効化するか。
    
- Realtime Transport Control Protocol (RTCP) パケットが送信される条件。
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化を要求するか。
    
ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、グローバル コレクション内のプロパティを既定値に「リセット」するには、Skype ビジネス サーバーのコントロール パネルの[削除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)コマンドレットを使用できます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。
  
管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。
  
- サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。
    
- サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype でのトランク構成の設定を削除するのには

1. ビジネス サーバーのコントロール パネルの Skype は、[**音声ルーティング**] をクリックしてで**トランクの構成**] をクリックします。
    
2. [**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**]、[**削除**] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。
    
3. コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。
    
4. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
    
5. **Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスで [ **OK**] をクリックします。
    
6. If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. **Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスが表示されたら、[ **OK**] をクリックします。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Skype ビジネス サーバーの管理シェル コマンドレットを使用してトランク構成設定を削除します。

Skype をビジネス サーバー管理シェルを**削除 CsTrunkConfiguration**コマンドレットを使用してトランク構成設定を削除できます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Skype のリモート セッションからサーバー管理シェルのビジネス。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>指定した設定のコレクションを削除するには

- 次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>サイト スコープに適用されているすべてのコレクションを削除するには

- 次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>メディア バイパスが有効になっているすべてのコレクションを削除するには

- 次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

詳細については、[削除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

