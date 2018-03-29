---
title: Skype for Business Server 2015 での QoE (Quality of Experience) の有効化
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '概要: ビジネス サーバー 2015 の高品質のエクスペリエンス (QoE) では、Skype を有効にする方法を説明します。'
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での QoE (Quality of Experience) の有効化
 
**の概要:**ビジネス サーバー 2015 の高品質のエクスペリエンス (QoE) では、Skype を有効にする方法について説明します。
  
QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。 詳細については、計画ドキュメントの[監視を計画する](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)を参照してください。
  
組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。
  
> [!NOTE]
> QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。 詳細については、[展開の監視](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)を参照してください。 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、QoE を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。 
    
4. [**QoE データ**] ページで、表から該当するコレクションをクリックして、[**アクション**]、[**QoE を有効にする**] の順にクリックします。
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、QoE を有効にします。

QoE を有効にするには、Windows PowerShell と**セット CsQoEConfiguration**コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-enable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を有効にするには

 QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を無効にするには

 QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>複数の場所の QoE を 1 つのコマンドで有効にするには

 このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

詳細については、[一連の CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)を参照してください。
  
## <a name="see-also"></a>関連項目

[監視の計画](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[監視を展開します。](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

