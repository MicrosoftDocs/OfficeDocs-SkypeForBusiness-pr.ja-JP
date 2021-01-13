---
title: Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 Stress and Performance Tool のポリシー構成。
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815037"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成
 
Skype for Business Server 2015 Stress and Performance Tool のポリシー構成。
  
Stress and Performance Tool を実行する前に、Skype for Business Server 2015 で構成できるいくつかのポリシーと他の領域があります。
  
- [アーカイブ ポリシー](configuring-policies.md#ArchivingPolicy)
    
- [会議ポリシー](configuring-policies.md#ConferencingPolicy)
    
- [連絡先ポリシー](configuring-policies.md#ContactsPolicy)
    
- [フェデレーション ポリシー](configuring-policies.md#FederationPolicy)
    
- [通話受付管理ポリシー](configuring-policies.md#CACPolicy)
    
- [音声ルーティング ルール](configuring-policies.md#VoiceRoutingRules)
    
- [会議アテンダント アプリケーション](configuring-policies.md#ConfAttendantApp)
    
- [サーバー コール パーク サービス](configuring-policies.md#ServerCallParkServ)
    
- [緊急電話](configuring-policies.md#EmergencyCalls)
    
- [応答グループ アプリケーションの構成](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>アーカイブ ポリシー
<a name="ArchivingPolicy"> </a>

Skype for Business Server トポロジにアーカイブ サーバーが展開されている場合は、次のスクリプトArchivingPolicy.ps1できます。 さらにサポートが必要な場合は、アーカイブと Web 会議のコマンドレットを確認してください。
  
## <a name="conferencing-policy"></a>会議ポリシー
<a name="ConferencingPolicy"> </a>

電話会議には、次のスクリプトMeetingPolicy.ps1があります。 さらにサポートが必要な場合は、Web 会議のコマンドレットを確認してください。
  
## <a name="contacts-policy"></a>連絡先ポリシー
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1は、確認する必要があるサンプルです。 さらに参照が必要な場合は、IM とプレゼンスのコマンドレットが役立ちます。
  
## <a name="federation-policy"></a>フェデレーション ポリシー
<a name="FederationPolicy"> </a>

フェデレーションのサンプル スクリプトはFederationPolicy.ps1。 詳細な情報が必要な場合に確認するコマンドレットは、エッジ サーバー、フェデレーション、および外部アクセスです。
  
## <a name="call-admission-control-policy"></a>通話受付管理ポリシー
<a name="CACPolicy"> </a>

このポリシーのBandwidthPolicy.ps1参照できます。 通話受付管理のコマンドレットには、さらに詳しい情報もあります。
  
## <a name="voice-routing-rules"></a>音声ルーティング ルール
<a name="VoiceRoutingRules"> </a>

音声ルーティングのサンプル スクリプトRoutingRules.ps1必要です。 これらのルールを構成する場合は、ユーザー作成時に指定できるよう、電話コンテキスト (/Location Profile または /SimpleName) と内部/外部エリア コードをメモします。 また、LyncPerfTool の構成中 (特に PSTN-UC および UC-PSTN 用) に必要になります。
  
たとえば、RoutingRules.ps1 の例の **New-CsDialPlan** コマンドレットの呼び出しの SimpleName パラメーターは、次の図の LocationProfile 値に使用UserProfileGenerator.exe。
  
![Skype for Business 読み込み構成ツール、音声シナリオ タブ、会話の詳細設定。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
詳細については、次のコマンドレットをエンタープライズ VoIPできます。
  
## <a name="conference-attendant-application"></a>会議アテンダント アプリケーション
<a name="ConfAttendantApp"> </a>

最初に、次のConferenceAutoAttendantConfiguration.ps1します。 次のように、LyncPerfTool 構成ツールに入力して構成を生成するために、ConferencingAutoAttendant 電話番号 (既定では 11211111111) をメモする必要があります。
  
![[音声シナリオ] タブに電話会議の負荷レベルと電話番号が表示されます。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
詳細については、電話会議とダイヤルイン会議のコマンドレットを参照してください。
  
## <a name="server-call-park-service"></a>サーバー コール パーク サービス
<a name="ServerCallParkServ"> </a>

これは、既定では実際には無効になっています。 テストする必要がある場合CallParkConfiguration.ps1サンプル スクリプトを確認できます。 さらに、コール パーク アプリケーションのコマンドレットを必要に応じて確認してください。
  
## <a name="emergency-calls"></a>緊急電話
<a name="EmergencyCalls"> </a>

緊急電話のストレステストとパフォーマンス テストを構成するには、次の手順を実行する必要があります。
  
1. 緊急電話のボイス ルートを設定します。 このボイス ルートの設定RoutingRules.ps1、"Route **E911 to PSTN"** というコメントの下で確認できます。
    
    > [!CAUTION]
    > 次のコマンド例RoutingRules.ps1 911 ではなく番号 119 を含む番号パターンです。 負荷テスト中に、911 (または実際のローカル緊急電話番号) を使用して、ローカルの緊急オペレーターへの偶発的な呼び出しを防ぐ必要があります。 この構成はシミュレーションのみを目的とします。 
  
2. 次の図に示すように、UserProvisioningTool の **[Location Info Service Config]** タブの値を入力して、アドレスを構成します。
    
     ![アドレス、サブネット、スイッチ、およびポートの数を示すユーザー プロビジョニング ツール。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. UserProvisioningTool にすべてを入力した後、[LIS 構成ファイルの生成] **ボタンをクリック** します。
    
4. ポート、サブネット、スイッチ、ワイヤレス アクセス ポイント (WAP) 用の CSV ファイルと、Stress and Performance ツール用の XML ファイルが生成されます。 このスクリプトを使用して場所情報サービス (LIS) を構成する場合は、入力に CSV ファイルLisConfiguration.ps1できます。 これを行うには、Locations0.xml ファイルを Stress and Performance Tool 実行可能ファイル (LyncPerfTool.exe) と同じフォルダーに移動する必要があります。 これにより、場所プロファイル (ダイヤル プラン) のシナリオを実行できます。
    
## <a name="configuring-response-group-application"></a>応答グループ アプリケーションの構成
<a name="ConfigResponseGroupApp"> </a>

サンプル スクリプトは次ResponseGroupConfiguration.ps1。 さらに構成の詳細を確認する応答グループ アプリケーションコマンドレットも用意されています。 次の図は、構成の詳細の一部を示しています。
  
![テスト用の既存のワークフローを示す応答グループ構成ツール。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

