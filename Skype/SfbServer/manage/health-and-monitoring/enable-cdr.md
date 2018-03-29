---
title: Skype for Business Server 2015 での通話詳細記録の有効化
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '概要: は、Skype でのビジネス サーバー 2015 (CDR) のレコードを記録呼び出しの詳細を有効にする方法を説明します。'
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での通話詳細記録の有効化
 
**の概要:**呼び出しの詳細 (CDR) のレコードを Skype のビジネス サーバー 2015 の記録を有効にする方法を説明します。
  
通話詳細記録 (CDR) は、インスタント メッセージング、ボイス オーバー IP (VoIP) 通話、アプリケーション共有、ファイル送信などのピアツーピア アクティビティ、および会議に関する使用状況および診断情報を記録します。使用状況データは投資収益率 (ROI) の計算に、診断データはピアツーピア アクティビティおよび会議のトラブルシューティングに使用できます。 
  
組織全体または組織内の各サイトで CDR を有効にするには、次の手順を実行します。
  
> [!NOTE]
> CDR を有効にするには、監視および監視データベースを構成する必要があります。 詳細については、[展開の監視](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)を参照してください。 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype で CDR を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。 
    
4. [**通話詳細記録**] ページで、表から該当するサイトをクリックして、[**アクション**] をクリックし、[**CDR の有効化**] をクリックします。
    
    > [!NOTE]
    > CDR は、既定では有効になっています。 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、CDR を有効にします。

CDR を有効にするには、Windows PowerShell と**セット CsCdrConfiguration**コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-enable-cdr-for-a-single-location"></a>1 つの場所の CDR を有効にするには

 CDR を無効にするには、EnableCDR パラメーターを True ($True) に設定します。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>1 つの場所の CDR を無効にするには

 CDR を無効にするには、EnableCDR パラメーターを False ($False) に設定します。CDR を無効にしても、監視がアンインストールされることはありません。CDR データの収集と保存が一時停止されます。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>1 つのコマンドで複数の場所にある CDR を有効にするには

 このコマンドによって、組織で現在使用されているすべての CDR 構成設定の CDR が有効になります。
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

詳細については、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[監視の計画](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[監視を展開します。](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)