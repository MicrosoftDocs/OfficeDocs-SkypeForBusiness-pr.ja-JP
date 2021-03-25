---
title: Skype for Business Server で -Roll を使用して AV 証明書と OAuth 証明書をステージSet-CsCertificate
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
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '概要: Skype for Business Server の AV 証明書と OAuth 証明書をステージします。'
ms.openlocfilehash: 87527d4bb51a5c38e0f85f72b299b67f235f2cf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119566"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Skype for Business Server で -Roll を使用して AV 証明書と OAuth 証明書をステージSet-CsCertificate
 
**概要:** Skype for Business Server の AV 証明書と OAuth 証明書をステージします。
  
音声/ビデオ (A/V) 通信は、Skype for Business Server の重要なコンポーネントです。 アプリケーション共有や音声ビデオ会議などの機能は、A/V Edge サービス、特に音声ビデオ認証サービスに割り当てられた証明書に依存します。
  
> [!IMPORTANT]
> この新機能は、A/V Edge サービスと OAuthTokenIssuer 証明書で動作するように設計されています。 その他の証明書の種類は、A/V Edge サービスと OAuth 証明書の種類と共にプロビジョニングできますが、A/V エッジ サービス証明書が実行する共存動作の利点はありません。
  
Skype for Business Server 証明書の管理に使用される Skype for Business Server 管理シェル PowerShell コマンドレットは、A/V エッジ サービス証明書を AudioVideoAuthentication 証明書の種類として、OAuthServer 証明書を typeOAuthTokenIssuer として参照します。 このトピックの残りの部分では、証明書を一意に識別するために、AudioVideoAuthentication とOAuthTokenIssuer という同じ識別子の種類で参照されます。
  
A/V 認証サービスは、クライアントや他の A/V コンシューマーによって使用されるトークンの発行を担当します。 トークンは証明書の属性から生成され、証明書の有効期限が切れると、接続が失われると、新しい証明書によって生成された新しいトークンに再び追加する必要があります。 Skype for Business Server の新機能は、この問題を軽減します。古い証明書の有効期限が切れて、両方の証明書が一時機能し続ける前に新しい証明書をステージする機能。 この機能は、Skype for Business Server 管理シェル コマンドレットSet-CsCertificate機能を使用します。 既存のパラメーター -EffectiveDate を持つ新しいパラメーター -Roll は、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 発行されたトークンを検証するために、古い AudioVideoAuthentication 証明書は引き続き残ります。 新しい AudioVideoAuthentication 証明書の設定から、次の一連のイベントが発生します。
  
> [!TIP]
> Skype for Business Server Management Shell コマンドレットを使用して証明書を管理すると、エッジ サーバー上の目的ごとに個別の証明書を要求できます。 Skype for Business Server 展開ウィザードで証明書ウィザードを使用すると、証明書の作成が支援されますが、通常は、エッジ サーバーで使用する証明書を 1 つの証明書に結合する既定の種類です。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 証明書の有効期限が切れたときにインスタント メッセージングの会話に参加するユーザーは、Access Edge サービスに関連付けられた新しい証明書を利用するために、ログアウトしてログインし戻す必要があります。 同様の動作は、Web 会議エッジ サービスを使用して Web 会議に関与するユーザーにも発生します。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 証明書は 1 か所で作成および管理し、証明書は他のすべてのサーバーの中央管理ストアに保存されます。
  
Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。 -Roll パラメーターは重要ですが、基本的には単一の目的です。 パラメーターとして定義する場合は、-Type (AudioVideoAuthentication や OAuthTokenIssuer など) によって定義される証明書に関する情報を提供する必要があることを Set-CsCertificate に伝えて、証明書が -EffectiveDate によって効果的に定義されます。
  
 **-Roll**: -Roll パラメーターは必須であり、依存関係と共に指定する必要があります。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。
  
 **-EffectiveDate**: パラメーター -EffectiveDate は、新しい証明書が現在の証明書と共同アクティブになる時間を定義します。 -EffectiveDate は、現在の証明書の有効期限に近い場合や、より長い期間である場合があります。 AudioVideoAuthentication 証明書の推奨最小 -EffectiveDate は 8 時間で、AudioVideoAuthentication 証明書を使用して発行される AV Edge サービス トークンの既定のトークン有効期間です。
  
OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。
  
 **-Thumbprint**: 拇印は証明書の属性で、証明書ごとに一意となります。 -Thumbprint パラメーターは、このコマンドレットのアクションの影響を受ける証明書を識別Set-CsCertificateします。
  
 **-Type**: -Type パラメーターは、単一の証明書使用法の種類または証明書の使用法の種類のコンマ区切りリストを受け入れられます。 証明書の種類は、コマンドレットとサーバーに対して、証明書の目的を識別する種類です。 たとえば、「AudioVideoAuthentication is use by the A/V Edge service and the AV Authentication service」と入力します。 異なる種類の証明書を同時に準備する場合は、証明書に必要な最小有効リードタイムを最も長く考慮する必要があります。 たとえば、AudioVideoAuthentication 型と OAuthTokenIssuer 型の証明書をステージ化する必要があります。 最小 -EffectiveDate は、2 つの証明書の中で大きい値である必要があります。この場合、OAuthTokenIssuer は、最小リード タイムが 24 時間です。 24 時間のリード タイムで AudioVideoAuthentication 証明書をステージ化しない場合は、要件に合った EffectiveDate を使用して個別にステージ化します。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll および -EffectiveDate パラメーターを使用して A/V Edge サービス証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. A/V Edge サービス上の既存の証明書のエクスポート可能なプライベート キーを使用して、更新または新しい AudioVideoAuthentication 証明書を要求します。
    
3. 新しい AudioVideoAuthentication 証明書をエッジ サーバーとプール内の他のすべてのエッジ サーバーにインポートします (プールが展開されている場合)。
    
4. インポートされた証明書を Set-CsCertificateコマンドレットで構成し、-EffectiveDate パラメーターと一緒に -Roll パラメーターを使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書をアクティブに設定する必要がある時間が与え、-EffectiveDate \<string\> : "7/22/2015 6:00:00 AM" になります。 
    
    > [!IMPORTANT]
    > エッジ プールでは、すべての AudioVideoAuthentication 証明書を展開し、新しい証明書を使用してすべてのクライアント トークンとコンシューマー トークンが更新される前に古い証明書が期限切れになった場合に発生する可能性がある音声ビデオ通信の中断を回避するために展開された最初の証明書の -EffectiveDate パラメーターによって定義された日付と時刻によって準備されている必要があります。 
  
    -roll Set-CsCertificate -EffectiveTime パラメーターを使用して、次のコマンドを実行します。
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Set-CsCertificate コマンドの例を次に示します。
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定と一致する形式である必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
Set-CsCertificate、-Roll、-EffectiveDate が使用するプロセスをさらに理解するために、新しい AudioVideoAuthentication トークンを発行するための新しい証明書をステージ化しながら、既存の証明書を使用してコンシューマーが使用している AudioVideoAuthentication を検証するには、視覚的なタイムラインがプロセスを理解する効果的な手段です。 次の例では、管理者は、A/V Edge サービス証明書の有効期限が 2015 年 7 月 22 日午後 2:00:00 になると判断します。 新しい証明書を要求して受信し、プール内の各エッジ サーバーにインポートします。 2015 年 7 月 22 日午前 2 時に、新しい証明書の拇印文字列に等しい -Roll、-Thumbprint を使用して Get-CsCertificate の実行を開始し、-EffectiveTime を 07/22/2015 6:00:00 AM に設定します。 各エッジ サーバーでこのコマンドを実行します。
  
![Roll パラメーターと EffectiveDate パラメーターを使用する。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stage**|
|:-----|:-----|
|1  <br/> |開始: 2015/7/22 12:00:00 AM  <br/> 現在の AudioVideoAuthentication 証明書は、2015 年 7 月 22 日午後 2 時に期限切れになる予定です。 これは、証明書の有効期限切れタイム スタンプによって決まります。 既存の証明書が有効期限に達する前に、証明書の交換とロールオーバーを計画して、8 時間の重複 (既定のトークンの有効期間) を考慮します。 この例では、2:00:00 AM のリード タイムを使用して、管理者が新しい証明書を 6:00:00 の有効時間より前に配置して準備するための十分な時間を確保します。  <br/> |
|2  <br/> |2015/7/22 2:00:00 AM - 7/22/2015 5:59:59 AM  <br/> Set-CsCertificate \<certificate usage type\> -Type -Thumbprint -Roll -EffectiveDate を使用して、有効な時間が 6:00:00 (この例では 4 時間のリード タイムですが、長くすることができます) のエッジ サーバーに証明書を \<thumbprint of new certificate\> 設定する \<datetime string of the effective time for new certificate\>  <br/> |
|3  <br/> |2015/7/22 6:00 AM - 7/22/2015 14:00  <br/> トークンを検証するには、新しい証明書が最初に試され、新しい証明書がトークンの検証に失敗した場合は、古い証明書が試されます。 このプロセスは、8 時間 (既定のトークンの有効期間) の重複期間中のすべてのトークンに使用されます。  <br/> |
|4  <br/> |終了: 2015/7/22 14:00:01  <br/> 古い証明書の有効期限が切れ、新しい証明書が引き継がれています。 古い証明書は、-Type -Previous Remove-CsCertificateで安全 \<certificate usage type\> に削除できます  <br/> |
   
有効時間に達すると (2015/7/22 6:00:00 AM)、すべての新しいトークンが新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れたら (2015/7/22 2:00:00 PM)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを使用Remove-CsCertificateコマンドレットを使用して安全に削除できます。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll および -EffectiveDate パラメーターを使用して OAuthTokenIssuer 証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. フロントエンド サーバー上の既存の証明書のエクスポート可能なプライベート キーを使用して、更新または新しい OAuthTokenIssuer 証明書を要求します。
    
3. 新しい OAuthTokenIssuer 証明書をプール内のフロント エンド サーバーにインポートします (プールが展開されている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新および書き換うだけで十分です。 フロントエンド サーバーを例に使用します。
    
4. インポートされた証明書を Set-CsCertificateコマンドレットで構成し、-EffectiveDate パラメーターと一緒に -Roll パラメーターを使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。 
    
    -roll Set-CsCertificate -EffectiveTime パラメーターを使用して、次のコマンドを実行します。
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Set-CsCertificate コマンドの例を次に示します。
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate は、サーバーの地域と言語の設定と一致する形式である必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
有効時間に達すると (2015/7/21 1:00:00 AM)、すべての新しいトークンが新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れたら (2015/7/22 2:00:00 PM)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを使用Remove-CsCertificateコマンドレットを使用して安全に削除できます。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>関連項目

[Skype for Business Server でサーバー間認証 (OAuth) とパートナー アプリケーションを管理する](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)