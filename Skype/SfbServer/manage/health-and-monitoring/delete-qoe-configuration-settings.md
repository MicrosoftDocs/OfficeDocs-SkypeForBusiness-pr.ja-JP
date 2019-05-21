---
title: Skype for Business Server の品質向上の設定を削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '概要: Skype for Business Server の Quality of Experience (QoE) 設定を削除する方法について説明します。'
ms.openlocfilehash: 4b521afd85a97550b27f320b9e49c5439e431681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305802"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server の品質向上の設定を削除する
 
**概要:** Skype for Business Server の Quality of Experience (QoE) 設定を削除する方法について説明します。
  
Quality of Experience (QoE) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
Skype for Business Server をインストールすると、QoE 構成設定のグローバルコレクションが1つ作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。
  
グローバル設定を "削除" することもできます。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。 仮にグローバル コレクションを変更して削除を無効にしたとします。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
QoE 構成設定を削除するには、Skype for Business Server コントロールパネルを使用するか、または[remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)コマンドレットを使用します。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して QoE 構成設定を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**OK**] をクリックします。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して QoE 構成設定を削除する

QoE 構成設定を削除するには、Windows PowerShell と**Remove-CsQoEConfiguration**コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>指定した QoE 構成設定のコレクションを削除するには

 このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されたすべての QoE 構成設定を削除するには

 このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効にされたすべての QoE 構成設定を削除するには

 このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

詳細については、「[削除-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で通話の記録とエクスペリエンスデータベースの再生の詳細を手動で削除する](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

