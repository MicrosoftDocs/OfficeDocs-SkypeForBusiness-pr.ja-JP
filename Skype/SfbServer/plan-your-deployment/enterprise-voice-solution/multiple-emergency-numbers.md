---
title: ビジネス サーバーに、Skype で複数の緊急番号を計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: ビジネス サーバーに、Skype で複数の緊急番号を計画する方法については、このトピックを参照してください。
ms.openlocfilehash: 6a27539641544682f6cb0905d8434f632fa868f2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23891522"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>ビジネス サーバーに、Skype で複数の緊急番号を計画します。
 
ビジネス サーバーに、Skype で複数の緊急番号を計画する方法については、このトピックを参照してください。
  
Skype ビジネス サーバーがクライアントの複数の緊急番号の構成をサポートしています。 複数の緊急番号は 2016年 6 月で導入された新しい機能を累積的な更新です。 米国の緊急電話番号 (911) は 1 つですが、多くの国では複数の緊急電話番号が利用されています。 など、英国では、999、英国では、特定の緊急電話番号と 112、欧州連合の緊急電話番号の両方をサポートします。 
  
また、この機能は、緊急事態の複数の緊急電話番号のローミングを利用できるようにしたい米国内の医療機関にも役立ちます。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>複数の緊急電話番号と場所のポリシー

どのように緊急時の呼び出しを定義するポリシーを実装する場所を作成することで緊急の呼び出しを構成します。 場所のポリシーを使用して、どのような番号は、緊急の呼び出しを構成する要素を定義するのには、米国の 911 など999 と英国で 112。 緊急の呼び出しの動作は、どのような緊急通話は、のユーザーが有効になっているかどうかおよびその、場所のポリシーが決定します。 かどうか企業のセキュリティを自動的に通知するか、および通話をルーティングする方法を定義することもできます。
  
定義して、場所のポリシーを変更する方法の詳細については、 [Skype のビジネス サーバーの場所のポリシーを計画](location-policies.md)し、 [Skype ビジネス サーバー用に作成する場所のポリシー](../../deploy/deploy-enterprise-voice/create-location-policies.md)を参照してください。 これらのトピックでは、場所のポリシーに関する概念を説明します。ただし、[ビジネス用の Skype で複数の緊急番号を構成する](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)複数の緊急番号を構成するのにはの指示を従う必要があります。
  
複数の緊急電話番号を計画する場合は、以下の点に留意してください。
  
- 2016年 6 月の累積的な更新は、5 つまでの緊急番号の特定の場所のポリシーを定義できます。 2016年 11 月の累積的な更新は、この数が 100 に増加します。
    
    > [!NOTE]
    > かどうかにないまだアップグレード 2016年 11 月累積的な更新は、 [Skype のビジネス サーバー 2015 への更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)を参照してください。 
  
- 各緊急電話番号では、一意に特定の場所のポリシーは、0 個以上の緊急ダイヤル マスクを指定できます。
    
    ダイヤル マスクは、ダイヤル時に、緊急ダイヤル番号の値に変換する番号です。 たとえば、このフィールドに "212" という値を入力し、緊急ダイヤル番号フィールドの値が "911" であるとします。 この場合、ユーザーが 212 をダイヤルすると、番号は 911 と解釈されます。 これで代替の緊急番号にダイヤルして、緊急サービスに到達する呼び出しは、(他のユーザーが国または地域別の緊急電話番号にダイヤルする国または地域の番号の番号ではなく、しよう場合など、国または地域に取り付けられている)。 値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。 たとえば、212;414 のように入力します。 ダイヤル マスクの文字列の制限は、100 文字です。 各文字は 0 ～ 9 の数字である必要があります。
    
- 各場所のポリシーには、公衆交換電話網 (PSTN) の使用法を 1 つ指定します。これは、このポリシーを使用するクライアントからの緊急通話のルーティングにどの音声ルートを使用するかを決定するために使用されます。使用法には、緊急電話番号ごとに一意のルートを指定できます。
    
- 場所ポリシーに EmergencyNumbers と DialString の両方のパラメーターがあり、クライアントが複数の緊急電話番号をサポートしている場合は、緊急電話番号が優先されます。 クライアントが複数の緊急電話番号をサポートしていない場合は、緊急ダイヤル文字列が使用されます。
    
- ビジネスおよび Lync にする Skype のクライアントは緊急番号が複数の受信をサポートして、マスク、および公衆交換電話網 (PSTN) 使用法をダイヤルについては、[クライアントのサポート](multiple-emergency-numbers.md#BKMK_Clients)を参照してください。
    
> [!NOTE]
> ビジネス コントロール パネルの Skype を使用して、複数の緊急番号を構成できません。 複数の緊急電話番号は、PowerShell を使用して構成する必要があります。 
  
複数の緊急電話番号を構成する前に、以下の点に留意してください。
  
- 複数の緊急番号を構成するのには新規 CsEmergencyNumber コマンドレットを使用する必要があり、[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)を EmergencyNumbers パラメーターを指定することによって 1 つ以上の緊急電話番号をサポートしている場所のポリシーを定義する必要があり、[セット CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットです。
    
- 	EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターを付けて Set-CsLocationPolicy コマンドレットまたは New-CsLocationPolicy コマンドレットを使用して定義された既存の番号がある場合、EmergencyNumbers パラメーターで指定された値が、古い値よりも優先されます。つまり、EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターの値は無視されます。
    
- セット CsLocationPolicy または新規 CsLocationPolicy コマンドレットを使用してパラメーターを使用して EmergencyDialString と EmergencyDialMask*新しい緊急時の番号を構成しないと*、定義されている既存の番号がある場合、既存の番号は引き続き使用します。
    
- 複数の緊急電話番号機能が機能するには、実行中のクライアント バージョンが新機能をサポートできる必要があります。 古いクライアントは、EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターを付けて Set-CsLocationPolicy コマンドレットまたは New-CsLocationPolicy コマンドレットで指定した古い値を使い続けます。 
    
- ユーザーがダイヤル文字列と一致する番号をダイヤルする場合、ダイヤル マスクは必要ありません。 たとえば、ユーザーがダイヤルする番号が 911 の場合、ダイヤル文字列は 911 であるため、マスクは必要ありません。 
    
複数の緊急番号を構成する方法の詳細については、[ビジネスの Skype の番号を複数の緊急時の構成](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)を参照してください。
  
次の表に、場所のポリシーの例を示します (例を示すことを目的としており、すべての属性が示されているわけではありません)。
  

|**場所のポリシー名**|**E911 有効**|**緊急ダイヤル文字列**|**ダイヤル マスク**|**緊急番号**|**PSTN 使用法**|**対象場所**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国  <br/> |はい  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |はい  <br/> |
|US-Hospital  <br/> |はい  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |はい  <br/> |
|ロンドン  <br/> |はい  <br/> |999  <br/> |144  <br/> |999 144  <br/> 112 911; 117 118  <br/> |GBEmergency  <br/> |不可  <br/> |
|India  <br/> |はい  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |いいえ  <br/> |
   
 **米国**複数の緊急番号の要件はありません。 アメリカ合衆国では、古い緊急電話番号とダイヤル マスク構成を使用します。
  
 **米国の病院**-「450」をマスクする必要があります。 複数の緊急番号をサポートしていないクライアントでは、古い緊急電話番号とダイヤル マスク構成を使用できます。 複数の緊急番号をサポートするクライアントでは、450 をマスキングではなく「450」と「911」両方の緊急電話の番号を指定できます。 します
  
 **ロンドン**-複数の緊急番号をサポートしていないクライアントでは、古い緊急電話番号とダイヤルのマスクの設定を使用することができます。 複数の緊急番号をサポートするクライアントでは、それぞれの「999」とマスクを使用した「112」の両方について、緊急電話番号を定義できます。 します
  
 **インド**: 展開済みのすべてのクライアントが複数の緊急番号をサポートします。 インドでのみ、複数の緊急番号を構成する必要があります。
  
## <a name="client-support"></a>クライアント サポート
<a name="BKMK_Clients"> </a>

次の表に、クライアントによる複数の緊急電話番号のサポート状況を示します。その他のクライアント サポートも引き続きテストされ、リリースされる予定です。定期的に再確認してください。

|**Windows **|**Version**|
|:-----|:-----|
|**クイック実行** <br/> |バージョン 1604 (ビルド 6868.2062) の 2016 - 5 月 10 日にリリースされた CC (現在のチャネル)  <br/> |
||FRDC (最新機能提供チャネルの最初のリリース) 2016 年 6 月 14 日リリース - バージョン 1605 (ビルド 6965.2058)  <br/> |
||DC (保留にされたチャネル) 2016 年 10 月 11 日リリース - バージョン 1605 (ビルド 6965.2092)  <br/> |
|**MSI** <br/> |6 月 7 日更新-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac と iOS** <br/> |**Version** <br/> |
||Skype for Mac クライアントのバージョン 16.9 のビジネス  <br/> ビジネス iOS クライアント バージョン 6.16 の Skype  <br/> |
|**Android** <br/> |**Version** <br/> |
||ビジネス Android クライアント バージョン 6.17 の Skype  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip Aastra 6725ip 電話 - 2016年 9 月の累積的な更新 (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 および HP 4120 電話 - 2016年 9 月の累積的な更新 (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||ポリコム CX500、CX600 のポリコム、およびポリコム CX3000 電話 - 2016年 9 月の累積的な更新 (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

