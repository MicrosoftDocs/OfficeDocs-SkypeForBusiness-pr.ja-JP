---
title: '[通話の詳細記録を有効にする] Skype for Business Server'
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: '概要: 通話詳細記録 (CDR) レコードを有効にする方法については、Skype for Business Server。'
ms.openlocfilehash: 1d09e637d75b9617abf669f75e96076333380a075010bd3d641f4c5189be9d89
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301383"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>[通話の詳細記録を有効にする] Skype for Business Server

**概要:** 通話詳細記録 (CDR) レコードを有効にする方法については、Skype for Business Server。

通話詳細記録 (CDR) は、インスタント メッセージング、ボイス オーバー IP (VoIP) 通話、アプリケーション共有、ファイル送信などのピアツーピア アクティビティ、および会議に関する使用状況および診断情報を記録します。使用状況データは投資収益率 (ROI) の計算に、診断データはピアツーピア アクティビティおよび会議のトラブルシューティングに使用できます。

組織全体または組織内の各サイトで CDR を有効にするには、次の手順を実行します。

> [!NOTE]
> CDR を有効にするには、監視および監視データベースを構成する必要があります。詳細については、「[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)」を参照してください。

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>コントロール パネルで CDR をSkype for Business Serverするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。

4. [**通話詳細記録**] ページで、表から該当するサイトをクリックして、[**アクション**] をクリックし、[**CDR の有効化**] をクリックします。

    > [!NOTE]
    > CDR は、既定では有効になっています。

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>複数のコマンドレットを使用して CDR をWindows PowerShellする

CDR を有効にするには、Windows PowerShell **Set-CsCdrConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した[Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、同じSkype for Business Server。

### <a name="to-enable-cdr-for-a-single-location"></a>1 つの場所の CDR を有効にするには

 CDR を無効にするには、EnableCDR パラメーターを True ($True) に設定します。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>1 つの場所の CDR を無効にするには

 CDR を無効にするには、EnableCDR パラメーターを False ($False) に設定します。 CDR を無効にしても、監視はアンインストールされない。 CDR データの収集と保存を一時停止します。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>1 つのコマンドで複数の場所にある CDR を有効にするには

 このコマンドによって、組織で現在使用されているすべての CDR 構成設定の CDR が有効になります。

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

詳細については [、Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目

[監視の計画](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[監視の展開](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)