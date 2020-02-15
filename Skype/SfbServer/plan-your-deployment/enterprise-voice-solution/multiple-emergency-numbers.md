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
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983022"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Skype for Business Server で複数の緊急電話番号を計画する
 
このトピックでは、Skype for Business Server で複数の緊急電話番号を計画する方法について説明します。
  
Skype for Business Server は、クライアントの複数の緊急電話番号の構成をサポートするようになりました。 複数の緊急電話番号は、2016年6月の累積的な更新プログラムで導入された新機能です。 米国には1つの緊急電話番号911がありますが、多くの国は複数の緊急電話番号をサポートしています。 たとえば、英国は、999、英国に固有の緊急電話番号、および欧州連合の緊急電話番号112の両方をサポートしています。 
  
また、この機能は、複数のコードに青の緊急電話番号をサポートする必要がある米国内の医療機関にも役立ちます。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>複数の緊急電話番号と場所のポリシー

緊急通話の実装方法を定義する場所ポリシーを作成して、緊急通話を構成します。 地域ポリシーを使用して、緊急電話を構成する番号 (米国の911など) を定義します。999および 112 (英国)。 場所のポリシーによって、ユーザーが緊急通話を有効にするかどうか、および緊急電話の動作についてが決まります。 また、企業のセキュリティを自動的に通知するかどうか、および通話をルーティングする方法を定義することもできます。
  
場所ポリシーの定義および変更の詳細については、「 [Plan location policies For skype for Business server](location-policies.md) 」および「 [Create Location policies In Skype for business server](../../deploy/deploy-enterprise-voice/create-location-policies.md)」を参照してください。 これらのトピックでは、場所のポリシーの概念について説明します。ただし、複数の緊急電話番号を構成するには、「 [Skype For business で複数の緊急電話番号を構成](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)する」の手順に従ってください。
  
複数の緊急電話番号を計画する場合は、次の点に注意してください。
  
- 2016年6月の累積的な更新プログラムでは、特定の場所のポリシーに対して最大5つの緊急電話番号を定義できます。 2016年11月の累積的な更新プログラムでは、この数は100に増加します。
    
    > [!NOTE]
    > 2016年11月の累積的な更新プログラムにまだアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。 
  
- 各緊急電話番号について、0個以上の緊急ダイヤルマスクを指定できます。これは、特定の場所ポリシーに固有のものです。
    
    ダイヤルマスクとは、ダイヤル時に緊急ダイヤル番号の値の値に変換する番号のことです。 たとえば、このフィールドに212の値を入力し、[緊急電話番号] フィールドの値を911にしたとします。 ユーザーが212にダイヤルすると、数値は911に変換されます。 これにより、別の緊急電話番号をダイヤルすることができます (たとえば、ある国または地域の他のユーザーが緊急電話番号ではなく、その国または地域の番号をダイヤルしようとした場合)現在の国または地域)。 値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。 例: 212; 414。 ダイヤルマスクの文字列の制限は、100文字です。 各文字は 0 ～ 9 の数字である必要があります。
    
- 各場所ポリシーには、このポリシーを使用するクライアントからの緊急電話のルーティングに使用される音声ルートを決定するために使用される単一の公衆交換電話網 (PSTN) の使用法があります。 使用法は、緊急電話番号ごとに固有のルートを持つことができます。
    
- 場所のポリシーで EmergencyNumbers パラメーターと tcp/ip 文字列パラメーターの両方が定義されており、クライアントが複数の緊急電話番号をサポートしている場合は、緊急電話番号が優先されます。 クライアントが複数の緊急電話番号をサポートしていない場合は、緊急ダイヤル文字列が使用されます。
    
- 複数の緊急電話番号、ダイヤルマスク、および公衆交換電話網 (PSTN) の使用法をサポートしている Skype for Business および Lync クライアントの詳細については、「[クライアントサポート](multiple-emergency-numbers.md#BKMK_Clients)」を参照してください。
    
> [!NOTE]
> Skype for Business コントロールパネルを使用して複数の緊急電話番号を構成することはできません。 複数の緊急電話番号を構成するには、PowerShell を使用する必要があります。 
  
複数の緊急電話番号を構成する前に、次の点に注意してください。
  
- 複数の緊急電話番号を構成するには、New-csemergencynumber コマンドレットを使用する必要があります。また、EmergencyNumbers パラメーターに[新しい-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)コマンドレットと[Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットを指定することによって、複数の緊急電話番号をサポートする場所のポリシーを定義する必要があります。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを指定して、パラメーターとパラメーターを使用して定義された既存の番号を使用している場合は、EmergencyNumbers パラメーターで指定した値が以前のバージョンよりも優先されます。数値. つまり、EmergencyDialString パラメーターと EmergencyDialMask パラメーターの値は無視されます。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して、既存の番号が定義されている場合、または新しい*緊急電話番号を構成*しない場合は、既存の番号が引き続き使用されます。
    
- 複数の緊急電話番号機能を機能させるには、実行しているクライアントバージョンが新機能をサポートできる必要があります。 以前のクライアントでは、EmergencyDialString パラメーターと EmergencyDialMask パラメーターを使用して、指定した古い値を引き続き使用します。 
    
- ユーザーがダイヤル文字列に一致する番号をダイヤルする場合は、ダイヤルマスクは必要ありません。 たとえば、ユーザーがダイヤルする番号が911の場合、ダイヤル文字列は911で、マスクは必要ありません。 
    
複数の緊急電話番号を構成する方法の詳細については、「 [Skype For business で複数の緊急電話番号を構成する](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)」を参照してください。
  
次の表に、場所のポリシーの例を示します (例では、すべての属性が表示されるわけではありません)。
  

|**場所のポリシー名**|**E911 enabled**|**緊急ダイヤル文字列**|**ダイヤルマスク**|**緊急電話番号**|**PSTN 使用法**|**必要な場所**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国  <br/> |はい  <br/> |911  <br/> | 112、999 <br/> ||USEmergency  <br/> |はい  <br/> |
|米病院  <br/> |はい  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |Seて Le救急  <br/> |はい  <br/> |
|北海道  <br/> |はい  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911、118  <br/> |GBEmergency  <br/> |いいえ  <br/> |
|インド  <br/> |はい  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |いいえ  <br/> |
   
 **米国**-複数の緊急電話番号の要件はありません。 米国では、以前の緊急ダイヤル文字列とダイヤルマスク構成を使用します。
  
 **米病院**-"450" をマスクする必要はありません。 まだ複数の緊急電話番号をサポートしていないクライアントでは、以前の緊急ダイヤル文字列とダイヤルマスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントでは、450をマスキングするのではなく、"911" と "450" の両方の緊急電話番号を定義できます。
  
 **London** —複数の緊急電話番号をまだサポートしていないクライアントの場合は、古い緊急ダイヤル文字列とダイヤルマスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントの場合、"999" と "112" の両方の緊急電話番号をそれぞれのマスクと共に定義できます。
  
 **インド**-展開されたすべてのクライアントが複数の緊急電話番号をサポートしています。 インドでは、複数の緊急電話番号を構成するだけでよい。
  
## <a name="client-support"></a>クライアント サポート
<a name="BKMK_Clients"> </a>

次の表は、複数の緊急電話番号のクライアントサポートを示しています。 Microsoft は、追加のクライアントのサポートを引き続きテストしてリリースします。 頻繁に確認してください。

|**Windows**|**バージョン**|
|:-----|:-----|
|**クイック実行** <br/> |CC (現在のチャネル) は2016年5月10日にリリースされました。バージョン 1604 (ビルド 6868.2062)  <br/> |
||FRDC (現在のチャネルの最初のリリース) は、2016年6月14日にリリースされました。バージョン 1605 (ビルド 6965.2058)  <br/> |
||DC (段階的提供チャネル) は、2016年10月11日にリリースされました。バージョン 1605 (ビルド 6965.2092)  <br/> |
|**MSI** <br/> |7月7日の更新プログラム-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac および iOS** <br/> |**バージョン** <br/> |
||Skype for Business Mac クライアントバージョン16.9  <br/> Skype for Business iOS クライアントバージョン6.16  <br/> |
|**Android** <br/> |**バージョン** <br/> |
||Skype for Business Android クライアントバージョン6.17  <br/> |
|**Lync Phone Edition** <br/> |**バージョン** <br/> |
|| Aastra 6721ip および Aastra 6721ip 電話機-9 月2016の累積的な更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 および HP 4120 電話機-9 月2016の累積的な更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600、および Polycom CX3000 電話-9 月2016の累積的な更新プログラム (ビルド 7577.4512)-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

