---
title: Skype for Business Server 2015 での QoE (Quality of Experience) 構成設定の削除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '概要: ビジネス サーバー 2015 の Skype の高品質のエクスペリエンス (QoE) の設定を削除する方法を説明します。'
ms.openlocfilehash: 52008e14ca7a7b2a7a26726a2749f6d4dd083bbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での QoE (Quality of Experience) 構成設定の削除
 
**の概要:**ビジネス サーバー 2015 の Skype の高品質のエクスペリエンス (QoE) の設定を削除する方法について説明します。
  
Quality of Experience (QoE) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
ビジネス サーバー 2015 年、1 つの Skype をインストールすると QoE 構成設定のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。
  
削除することも""グローバル設定に注意してください。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。 仮にグローバル コレクションを変更して削除を無効にしたとします。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
ビジネス サーバーのコントロール パネルの Skype を使用して、または[削除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)コマンドレットを使用して、QoE 構成設定を削除できます。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、QoE 構成設定を削除するのには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。 詳細については、**セットアップのアクセス許可の委任**を参照してください。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**OK**] をクリックします。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、QoE 構成設定を削除します。

QoE 構成設定を削除するには、Windows PowerShell と**削除 CsQoEConfiguration**コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
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

詳細については、[削除 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)を参照してください。
  
## <a name="see-also"></a>関連項目

[ビジネス サーバー 2015 の通話の詳細記録と Skype で高品質なエクスペリエンスのデータベースを手動で削除します。](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

