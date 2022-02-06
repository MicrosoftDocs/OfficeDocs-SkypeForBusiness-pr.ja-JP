---
title: '[通話パークの設定] を [Skype for Business'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: '[通話パーク] の設定を変更Skype for Business Server エンタープライズ VoIP。'
---

# <a name="configure-call-park-settings-in-skype-for-business"></a>[通話パークの設定] を [Skype for Business

[通話パーク] の設定を変更Skype for Business Server エンタープライズ VoIP。

既定の通話パーク設定を使用しない場合は、カスタマイズできます。 Call Park アプリケーションをインストールすると、既定でグローバル設定が構成されます。 グローバル設定を変更したり、サイト固有の設定を指定することもできます。 **New-CsCpsConfiguration** コマンドレットを使用して、新しいサイト固有の設定を作成します。 **Set-CsCpsConfiguration** コマンドレットを使用して、既存の設定を変更します。

> [!NOTE]
> 少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [**OnTimeoutURI**] オプションは構成することをお勧めします。

**New-CsCpsConfiguration** コマンドレットまたは **Set-CsCpsConfiguration** コマンドレットを使用して、次のいずれかの設定を構成します。


| **このオプション:**                     | **指定する内容:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。  <br/> この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。 最小値は 10 秒、最大値は 10 分です。 既定値は 00:01:30 です。  <br/> |
| **EnableMusicOnHold** <br/>          | 通話が保留されている間、発信者に対して音楽を再生するかどうか。  <br/> 値は True または False です。既定値は True です。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 保留された通話が [**OnTimeoutURI**] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | **MaxCallPickupAttempts** を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。 <br/> 値は、文字列 sip: で始まる SIP URI にする必要があります。 たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>通話パークの設定を構成するには

1. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. 次のコマンドを実行します。

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > サイトを識別するには、**Get-CsSite** コマンドレットを使用します。 詳細については、「管理シェルSkype for Business Server」を参照してください。

    次に例を示します。

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>関連項目

[Skype for Business 2015 で通話パークの音楽を保留にカスタマイズする](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)