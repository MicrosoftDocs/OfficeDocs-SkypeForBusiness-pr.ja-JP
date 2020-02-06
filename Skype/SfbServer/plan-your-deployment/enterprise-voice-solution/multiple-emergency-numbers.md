---
title: Skype for Business Server で複数の緊急電話番号を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: このトピックでは、Skype for Business Server で複数の緊急電話番号を計画する方法について説明します。
ms.openlocfilehash: 6f10b5c22a26a42f33f2a3b453dd2e244c9f32ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815965"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Skype for Business Server で複数の緊急電話番号を計画する
 
このトピックでは、Skype for Business Server で複数の緊急電話番号を計画する方法について説明します。
  
Skype for Business Server で、クライアントの複数の緊急電話番号の構成がサポートされるようになりました。 複数の緊急電話番号は、2016年6月の累積更新プログラムで導入された新機能です。 米国の緊急電話番号 (911) は 1 つですが、多くの国では複数の緊急電話番号が利用されています。 たとえば、英国は、999、英国に固有の緊急電話番号、および 112 (欧州連合の緊急電話番号) の両方をサポートしています。 
  
また、この機能は、緊急事態の複数の緊急電話番号のローミングを利用できるようにしたい米国内の医療機関にも役立ちます。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>複数の緊急電話番号と場所のポリシー

緊急通話の実装方法を定義する場所のポリシーを作成して、緊急通話を構成します。 地域ポリシーを使って、緊急通話に使用する番号 (米国の911など) を定義します。英国の999および112。 位置情報ポリシーは、ユーザーが緊急通話を有効にしているかどうかを決定し、場合によっては緊急通話の動作を決定します。 また、企業のセキュリティに自動的に通知するかどうかと、通話をルーティングする方法を定義することもできます。
  
位置情報ポリシーの定義と変更の詳細については、「skype for business [server の場所のポリシーを計画](location-policies.md)する」および「 [Skype for business server で場所のポリシーを作成](../../deploy/deploy-enterprise-voice/create-location-policies.md)する」を参照してください。 次のトピックでは、場所のポリシーに関する概念について説明します。ただし、複数の緊急電話番号を構成するには、「 [Skype For business の複数の緊急電話番号を構成](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)する」の手順に従う必要があります。
  
複数の緊急電話番号を計画する場合は、以下の点に留意してください。
  
- 2016年6月の累積更新プログラムでは、特定の場所ポリシーに対して、最大5つの緊急電話番号を定義できます。 2016年11月の累積更新プログラムでは、この数値は100よりも大きくなります。
    
    > [!NOTE]
    > 2016年11月の累積更新プログラムにアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。 
  
- 各緊急電話番号について、0個以上の緊急ダイヤルのマスクを指定できます。これは、特定の場所ポリシーに固有のものです。
    
    ダイヤル マスクは、ダイヤル時に、緊急ダイヤル番号の値に変換する番号です。 たとえば、このフィールドに "212" という値を入力し、緊急ダイヤル番号フィールドの値が "911" であるとします。 この場合、ユーザーが 212 をダイヤルすると、番号は 911 と解釈されます。 これにより、別の緊急電話番号をダイヤルすることができます。たとえば、別の緊急電話番号を持つ国または地域のユーザーは、その国または地域の番号ではなく、その国または地域の電話番号にダイヤルします。現在の国または地域)。 値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。 たとえば、212;414 のように入力します。 ダイヤルマスクの文字列の制限は、100文字です。 各文字は 0 ～ 9 の数字である必要があります。
    
- 各場所のポリシーには、公衆交換電話網 (PSTN) の使用法を 1 つ指定します。これは、このポリシーを使用するクライアントからの緊急通話のルーティングにどの音声ルートを使用するかを決定するために使用されます。使用法には、緊急電話番号ごとに一意のルートを指定できます。
    
- 場所ポリシーに EmergencyNumbers と DialString の両方のパラメーターがあり、クライアントが複数の緊急電話番号をサポートしている場合は、緊急電話番号が優先されます。 クライアントが複数の緊急電話番号をサポートしていない場合は、緊急ダイヤル文字列が使用されます。
    
- 複数の緊急電話番号、ダイヤルマスク、公衆交換電話網 (PSTN) の使用をサポートしている Skype for Business および Lync クライアントの詳細については、「[クライアントサポート](multiple-emergency-numbers.md#BKMK_Clients)」を参照してください。
    
> [!NOTE]
> Skype for ビジネスコントロールパネルを使用して、複数の緊急電話番号を構成することはできません。 複数の緊急電話番号は、PowerShell を使用して構成する必要があります。 
  
複数の緊急電話番号を構成する前に、以下の点に留意してください。
  
- 複数の緊急電話番号を構成するには、CsEmergencyNumber コマンドレットを使用する必要があります。また、[新しい](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)EmergencyNumbers[パラメーターを指定](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)すると、複数の緊急電話番号をサポートする場所ポリシーを定義する必要があります。
    
- 	EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターを付けて Set-CsLocationPolicy コマンドレットまたは New-CsLocationPolicy コマンドレットを使用して定義された既存の番号がある場合、EmergencyNumbers パラメーターで指定された値が、古い値よりも優先されます。つまり、EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターの値は無視されます。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して、Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットを使用して定義された既存の番号がある場合、*新しい緊急電話番号を構成しないと*、既存の電話番号がそのまま使用されます。
    
- 複数の緊急電話番号機能が機能するには、実行中のクライアント バージョンが新機能をサポートできる必要があります。 古いクライアントは、EmergencyDialString パラメーターおよび EmergencyDialMask パラメーターを付けて Set-CsLocationPolicy コマンドレットまたは New-CsLocationPolicy コマンドレットで指定した古い値を使い続けます。 
    
- ユーザーがダイヤル文字列と一致する番号をダイヤルする場合、ダイヤル マスクは必要ありません。 たとえば、ユーザーがダイヤルする番号が 911 の場合、ダイヤル文字列は 911 であるため、マスクは必要ありません。 
    
複数の緊急電話番号を設定する方法について詳しくは、「 [Skype For business の複数の緊急電話番号を設定する](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)」をご覧ください。
  
次の表に、場所のポリシーの例を示します (例を示すことを目的としており、すべての属性が示されているわけではありません)。
  

|**場所のポリシー名**|**E911 有効**|**緊急ダイヤル文字列**|**ダイヤル マスク**|**緊急電話番号**|**PSTN 使用法**|**対象場所**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国  <br/> |あり  <br/> |911  
  <br/> | 112;999 <br/> ||USEmergency  <br/> |はい  <br/> |
|US-Hospital  <br/> |はい  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |はい  <br/> |
|ロンドン  <br/> |はい  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112-911、117、118  <br/> |GBEmergency  <br/> |不可  <br/> |
|India  <br/> |はい  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |いいえ  <br/> |
   
 **米国**: 複数の緊急電話番号を使用する必要はありません。 米国では、古い緊急ダイヤルの文字列とダイヤルマスクの設定を使用します。
  
 **米病院**-"450" にマスクする必要はありません。 複数の緊急電話番号をまだサポートしていないクライアントの場合は、以前の緊急ダイヤルの文字列とダイヤルマスクの構成を使用できます。 複数の緊急電話番号をサポートしているクライアントの場合は、450をマスキングする代わりに、"911" と "450" の両方の緊急電話番号を定義できます。
  
 **ロンドン**: 複数の緊急電話番号をまだサポートしていないクライアントの場合、以前の緊急ダイヤルの文字列とダイヤルマスクの構成を使用できます。 複数の緊急電話番号をサポートしているクライアントの場合は、それぞれのマスクを使用して "999" と "112" の緊急電話番号を定義できます。
  
 **インド**: 展開されたすべてのクライアントが、複数の緊急電話番号をサポートしています。 インドでは、複数の緊急電話番号を設定する必要があります。
  
## <a name="client-support"></a>クライアント サポート
<a name="BKMK_Clients"> </a>

次の表に、クライアントによる複数の緊急電話番号のサポート状況を示します。その他のクライアント サポートも引き続きテストされ、リリースされる予定です。定期的に再確認してください。

|**Windows **|**バージョン**|
|:-----|:-----|
|**クイック実行** <br/> |2016年5月10日にリリースされた CC (現在のチャネル)-バージョン 1604 (ビルド 6868.2062)  <br/> |
||FRDC (最新機能提供チャネルの最初のリリース) 2016 年 6 月 14 日リリース - バージョン 1605 (ビルド 6965.2058)  <br/> |
||DC (保留にされたチャネル) 2016 年 10 月 11 日リリース - バージョン 1605 (ビルド 6965.2092)  <br/> |
|**MSI** <br/> |6月7日の更新プログラム-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac および iOS** <br/> |**バージョン** <br/> |
||Skype for Business Mac クライアントバージョン16.9  <br/> Skype for Business iOS クライアントバージョン6.16  <br/> |
|**Android** <br/> |**バージョン** <br/> |
||Skype for Business Android クライアントバージョン6.17  <br/> |
|**Lync Phone Edition** <br/> |**バージョン** <br/> |
|| Aastra 6721ip および Aastra 6721ip 電話-2016 年9月の累積更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 および HP 4120 電話-2016 年9月の累積更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600、Polycom CX3000 電話-2016 年9月の累積更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

