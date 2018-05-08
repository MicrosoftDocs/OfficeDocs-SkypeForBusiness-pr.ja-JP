---
title: Skype for Business 2015 でのコール パーク設定の構成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Skype ビジネス サーバーのエンタープライズ VoIP のコール パーク設定を変更します。
ms.openlocfilehash: 8f4aa5025cbe364a44a45632ebcdf852ad6a65bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>Skype for Business 2015 でのコール パーク設定の構成
 
Skype ビジネス サーバーのエンタープライズ VoIP のコール パーク設定を変更します。
  
コール パークの既定の設定を使用しない場合は、それらをカスタマイズできます。 コール パーク アプリケーションをインストールすると、グローバル設定は、既定で構成されます。 グローバルの設定を変更することができ、サイト固有の設定を指定することもできます。 **新規 CsCpsConfiguration**コマンドレットを使用すると、サイト固有の設定を新しいを作成します。 **セット CsCpsConfiguration**コマンドレットを使用して、既存の設定を変更します。
  
> [!NOTE]
> 少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [**OnTimeoutURI**] オプションは構成することをお勧めします。
  
次の設定のいずれかを構成するのにには、**新規 CsCpsConfiguration**コマンドレットまたは**セット CsCpsConfiguration**コマンドレットを使用します。
  
|**このオプション:**|**これを指定します。**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。  <br/> この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。最小値は 10 秒、最大値は 10 分です。既定値は 00:01:30 です。  <br/> |
|**EnableMusicOnHold** <br/> |通話が保留されている間、発信者に対して音楽を再生するかどうか。  <br/> 値は True または False です。既定値は True です。  <br/> |
|**MaxCallPickupAttempts** <br/> |保留された通話が [**OnTimeoutURI**] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。<br/> |
|**OnTimeoutURI** <br/> |**MaxCallPickupAttempts** を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。 <br/> 値は、文字列 sip: で始まる SIP URI にする必要があります。たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。<br/> |
   
### <a name="to-configure-call-park-settings"></a>コール パーク設定を構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行します。
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > サイトを識別するのにには、 **Get CsSite**コマンドレットを使用します。 詳細については、Lync Server 管理シェルのマニュアルを参照してください。
  
    例:
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>関連項目

#### 

[ビジネス 2015年の保留中の inSkype のコール パークの音楽をカスタマイズします。](customize-call-park-music-on-hold.md)
#### 

[新しい-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[セット CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Get CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

