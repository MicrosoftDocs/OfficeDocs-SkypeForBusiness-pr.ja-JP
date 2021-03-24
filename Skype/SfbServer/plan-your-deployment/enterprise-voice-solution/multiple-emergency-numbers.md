---
title: Skype for Business Server で複数の緊急電話番号を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server で複数の緊急電話番号を計画する方法については、このトピックを参照してください。
ms.openlocfilehash: 47ac1a93a39a95710bf1581aace0ec12a39caec6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101603"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Skype for Business Server で複数の緊急電話番号を計画する
 
Skype for Business Server で複数の緊急電話番号を計画する方法については、このトピックを参照してください。
  
Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。 複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。 米国の緊急電話番号は 1 つの 911 ですが、多くの国で複数の緊急電話番号がサポートされています。 たとえば、英国では、英国固有の緊急電話番号である 999 と、欧州連合の緊急電話番号 112 の両方がサポートされています。 
  
この機能は、複数のコード青色の緊急電話番号のローミングサポートを必要としている米国内の医療プロバイダーにも役立ちます。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>複数の緊急電話番号と場所ポリシー

緊急通話の実装方法を定義する場所ポリシーを作成して、緊急通話を構成します。 場所ポリシーを使用して、緊急通話を構成する番号 (米国の 911 など) を定義します。イギリスの 999 と 112。 場所ポリシーは、ユーザーが緊急通話を有効にするかどうかを決定し、緊急通話の動作が有効かどうかを決定します。 また、企業のセキュリティを自動的に通知するかどうかを定義し、通話のルーティング方法を定義することもできます。
  
場所ポリシーの定義と変更の詳細については [、「Skype for Business Server](location-policies.md) の場所ポリシーを計画する」および「Create location [policies in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/create-location-policies.md)。 これらのトピックでは、場所ポリシーに関する概念について説明します。ただし [、「Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) で複数の緊急電話番号を構成して複数の緊急電話番号を構成する」の指示に従う必要があります。
  
複数の緊急電話番号を計画する場合は、次の注意が必要です。
  
- 2016 年 6 月の累積的な更新プログラムでは、特定の場所ポリシーに対して最大 5 つの緊急電話番号を定義できます。 2016 年 11 月の累積的な更新プログラムでは、この数は 100 に増加します。
    
    > [!NOTE]
    > 2016 年 11 月の累積的な更新プログラムにまだアップグレードしていない場合は [、「Update to Skype for Business Server 2015」を参照](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)してください。 
  
- 緊急電話番号ごとに、特定の場所ポリシーに固有の 0 個以上の緊急ダイヤル マスクを指定できます。
    
    ダイヤル マスクは、ダイヤル時に緊急ダイヤル番号の値に変換する番号です。 たとえば、このフィールドに値 212 を入力し、緊急ダイヤル番号フィールドの値が 911 であるとします。 ユーザーが 212 をダイヤルすると、番号は 911 に変換されます。 これにより、代替緊急電話番号がダイヤルされ、通話が緊急サービスに届きます (たとえば、別の緊急電話番号を持つ国または地域のユーザーが、現在の国または地域の番号ではなく、その国または地域の番号にダイヤルしようとした場合)。 値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。 たとえば、212;414。 ダイヤル マスクの文字列制限は 100 文字です。 各文字は 0 ～ 9 の数字である必要があります。
    
- 各場所ポリシーには、このポリシーを使用するクライアントからの緊急通話のルーティングに使用される音声ルートを決定するために使用される、1 つの公衆交換電話網 (PSTN) 使用法があります。 使用状況には、緊急電話番号ごとに一意のルートを指定できます。
    
- 場所ポリシーに EmergencyNumbers パラメーターと DialString パラメーターの両方が定義され、クライアントが複数の緊急電話番号をサポートしている場合は、緊急番号が優先されます。 クライアントが複数の緊急電話番号をサポートしていない場合は、緊急ダイヤル文字列が使用されます。
    
- 複数の緊急電話番号、ダイヤル マスク、公衆交換電話網 (PSTN) の使用法の受信をサポートする Skype for Business クライアントと Lync クライアントの詳細については、「クライアント サポート」を [参照してください](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> Skype for Business コントロール パネルを使用して複数の緊急電話番号を構成することはできません。 PowerShell を使用して複数の緊急電話番号を構成する必要があります。 
  
複数の緊急電話番号を構成する前に、次の注意が必要です。
  
- 複数の緊急電話番号を構成するには、New-CsEmergencyNumber コマンドレットを使用する必要があります。 [また、New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットで EmergencyNumbers パラメーターを指定して、複数の緊急番号をサポートする場所ポリシーを定義する必要があります。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットを使用して既存の番号を定義している場合、EmergencyNumbers パラメーターで指定された値は、古い値よりも優先されます。 つまり、EmergencyDialString パラメーターと EmergencyDialMask パラメーターの値は無視されます。
    
- emergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットを使用して既存の番号を定義し、新しい緊急番号を構成しない場合、既存の番号は引き続き使用されます。
    
- 複数の緊急電話番号機能を機能するには、実行しているクライアント バージョンが新しい機能をサポートできる必要があります。 古いクライアントは、EmergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して、Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットで指定された古い値を引き続き使用します。 
    
- ユーザーがダイヤル文字列に一致する番号をダイヤルする場合、ダイヤル マスクは必要ありません。 たとえば、ユーザーがダイヤルする番号が 911 の場合、ダイヤル文字列は 911 で、マスクは必要ありません。 
    
複数の緊急電話番号の構成の詳細については、「Skype for Business で複数の緊急 [電話番号を構成する」を参照してください](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
次の表に、場所ポリシーの例を示します (この例では、すべての属性が表示される場合ではありません)。
  

|**場所ポリシー名**|**E911 が有効**|**緊急ダイヤル文字列**|**ダイヤル マスク**|**緊急電話番号**|**PSTN 使用法**|**必要な場所**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国  <br/> |はい  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |はい  <br/> |
|US-Hospital  <br/> |はい  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |はい  <br/> |
|ロンドン  <br/> |はい  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |いいえ  <br/> |
|インド  <br/> |はい  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |いいえ  <br/> |
   
 **米国** -複数の緊急電話番号の要件はありません。 米国では、古い緊急ダイヤル文字列とダイヤル マスク構成を使用します。
  
 **US-Hospital** :"450" をマスクしないという要件があります。 複数の緊急電話番号をまだサポートしていないクライアントの場合は、古い緊急ダイヤル文字列とダイヤル マスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントの場合は、450 をマスクする代わりに、"911" と "450" の両方の緊急電話番号を定義できます。
  
 **London** :複数の緊急電話番号をまだサポートしていないクライアントの場合は、古い緊急ダイヤル文字列とダイヤル マスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントの場合は、"999" と "112" の両方に対して、それぞれマスクを使用して緊急電話番号を定義できます。
  
 **インド** :展開されているクライアントはすべて、複数の緊急電話番号をサポートします。 インドでは、複数の緊急電話番号を構成する必要があります。
  
## <a name="client-support"></a>クライアント サポート
<a name="BKMK_Clients"> </a>

次の表に、複数の緊急電話番号のクライアント サポートを示します。 Microsoft は引き続き、追加のクライアントのサポートをテストおよびリリースします。 頻繁に確認してください。

|**Windows**|**バージョン**|
|:-----|:-----|
|**クイック実行** <br/> |2016 年 5 月 10 日にリリースされた CC (Current Channel) - バージョン 1604 (ビルド 6868.2062)  <br/> |
||2016 年 6 月 14 日にリリースされた FRDC (First Release Current Channel) - バージョン 1605 (ビルド 6965.2058)  <br/> |
||2016 年 10 月 11 日にリリースされた DC (遅延チャネル) - バージョン 1605 (ビルド 6965.2092)  <br/> |
|**MSI** <br/> |6 月 7 日の更新プログラム - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac と iOS** <br/> |**バージョン** <br/> |
||Skype for Business Mac クライアント バージョン 16.9  <br/> Skype for Business iOS クライアント バージョン 6.16  <br/> |
|**Android** <br/> |**バージョン** <br/> |
||Skype for Business Android クライアント バージョン 6.17  <br/> |
|**Lync Phone Edition** <br/> |**バージョン** <br/> |
|| Aastra 6721ip および Aastra 6725ip 電話 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 および HP 4120 電話 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600、Polycom CX3000 電話 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
