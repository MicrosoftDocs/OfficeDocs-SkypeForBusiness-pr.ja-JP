---
title: Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Skype for Business Server 2015 のストレスとパフォーマンスツールのポリシー構成。
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816196"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する
 
Skype for Business Server 2015 のストレスとパフォーマンスツールのポリシー構成。
  
「Skype for Business Server 2015 では、ストレスとパフォーマンスのツールを実行する前に構成できるいくつかのポリシーとその他の領域があります。
  
- [アーカイブポリシー](configuring-policies.md#ArchivingPolicy)
    
- [会議ポリシー](configuring-policies.md#ConferencingPolicy)
    
- [連絡先ポリシー](configuring-policies.md#ContactsPolicy)
    
- [フェデレーションポリシー](configuring-policies.md#FederationPolicy)
    
- [通話受付制御ポリシー](configuring-policies.md#CACPolicy)
    
- [ボイスルーティングルール](configuring-policies.md#VoiceRoutingRules)
    
- [会議アテンダントアプリケーション](configuring-policies.md#ConfAttendantApp)
    
- [サーバーコールパークサービス](configuring-policies.md#ServerCallParkServ)
    
- [緊急通話](configuring-policies.md#EmergencyCalls)
    
- [応答グループアプリケーションを構成する](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>アーカイブポリシー
<a name="ArchivingPolicy"> </a>

Skype for Business Server トポロジにアーカイブサーバーが展開されている場合は、ArchivingPolicy スクリプトを参照してください。 さらにサポートが必要な場合は、「アーカイブと Web 会議のコマンドレット」をご覧ください。
  
## <a name="conferencing-policy"></a>会議ポリシー
<a name="ConferencingPolicy"> </a>

会議の場合は、"会議ポリシー. ps1" スクリプトを使います。 さらにサポートが必要な場合は、「Web 会議コマンドレット」をご覧ください。
  
## <a name="contacts-policy"></a>連絡先ポリシー
<a name="ContactsPolicy"> </a>

ContactsPolicy スクリプトは、確認する必要があるサンプルです。 IM とプレゼンスのコマンドレットは、さらに参照が必要な場合に役立ちます。
  
## <a name="federation-policy"></a>フェデレーションポリシー
<a name="FederationPolicy"> </a>

フェデレーションのサンプルスクリプトは FederationPolicy です。 さらに詳しい情報が必要な場合は、確認するコマンドレットはエッジサーバー、フェデレーション、外部アクセスになります。
  
## <a name="call-admission-control-policy"></a>通話受付制御ポリシー
<a name="CACPolicy"> </a>

このポリシーについては、BandwidthPolicy を参照してください。 通話受付制御コマンドレットについては、さらに詳しい情報も含まれています。
  
## <a name="voice-routing-rules"></a>ボイスルーティングルール
<a name="VoiceRoutingRules"> </a>

ボイスルーティング用の RoutingRules サンプルスクリプトが必要です。 これらのルールを構成している場合は、電話のコンテキスト (¥ Location Profile または/simplename) と内部または外部の市外局番をメモして、ユーザーを作成するときに指定できます。 また、LyncPerfTool 構成 (特に PSTN-UC および UC-PSTN 用) でも必要になります。
  
たとえば、RoutingRules の例の**CsDialPlan**コマンドレットの呼び出しの simplename パラメーターは、UserProfileGenerator の次の図の locationprofile 値として使用する必要があります。
  
![Skype for Business Load Configuration Tool、[Voice Scenarios] タブ、会話の詳細設定](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
詳細については、「エンタープライズボイスのコマンドレット」を参照してください。
  
## <a name="conference-attendant-application"></a>会議アテンダントアプリケーション
<a name="ConfAttendantApp"> </a>

まず、ConferenceAutoAttendantConfiguration スクリプトを確認します。 ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモしておくと、次のように、これを LyncPerfTool 構成ツールに入力して構成を生成することができます。
  
![電話会議負荷レベルと電話番号を表示している [Voice Scenarios] タブ](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
詳細については、「会議とダイヤルイン会議のコマンドレット」を参照してください。
  
## <a name="server-call-park-service"></a>サーバーコールパークサービス
<a name="ServerCallParkServ"> </a>

これは、実際には既定では無効になっています。 これをテストする必要がある場合は、CallParkConfiguration. ps1 サンプルスクリプトを確認できます。 さらに、必要に応じて、コールパークアプリケーションのコマンドレットもご覧ください。
  
## <a name="emergency-calls"></a>緊急通話
<a name="EmergencyCalls"> </a>

緊急通話のストレスとパフォーマンスのテストを構成するには、次の手順を実行する必要があります。
  
1. 緊急通話のためのボイスルートを設定します。 このボイスルートの設定方法の例については、RoutingRules スクリプトを使用して、コメント " **E911 へのルーティング**" を確認してください。
    
    > [!CAUTION]
    > RoutingRules の例のコマンドには、911ではなく数値119を含む数値パターンが含まれています。 ロードテスト中に、お客様の地域の緊急対応オペレーターへの偶発的な通話を防ぐため、911 (または実際のローカル緊急電話番号) の使用は避けてください。 この構成はシミュレーション目的でのみ使用することに注意してください。 
  
2. 次の図に示すように、Userプロビジョニングツールの [**位置情報] サービス構成**タブの値を入力して、アドレスを構成します。
    
     ![アドレス、サブネット、スイッチ、ポートの数を表示している User Provisioning Tool](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Userプロビジョニングツールにすべての情報を入力したら、[ **LIS 構成ファイルの生成**] ボタンをクリックします。
    
4. これにより、ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、およびストレスとパフォーマンスツールの XML ファイルが生成されます。 LisConfiguration スクリプトを使用して位置情報サービス (LIS) を構成するときに、CSV ファイルを入力用に使うことができます。 そのためには、Locations0 ファイルを、ストレスとパフォーマンスツールの実行可能ファイル (LyncPerfTool) と同じフォルダーに移動する必要があります。 これにより、位置情報プロファイル (ダイヤルプラン) のシナリオを実行できるようになります。
    
## <a name="configuring-response-group-application"></a>応答グループアプリケーションを構成する
<a name="ConfigResponseGroupApp"> </a>

サンプルスクリプトは ResponseGroupConfiguration. ps1 です。 さらに構成の詳細を確認する応答グループのアプリケーションコマンドレットもあります。 次の図は、構成の詳細の一部を示しています。
  
![既存のテスト用ワークフローを表示している Response Group Configuration Tool](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

