---
title: 2015 年 2015 年Skype for Business Serverパフォーマンス ツールのポリシーの構成
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 2015 年Skype for Business Serverパフォーマンス ツールのポリシー構成。
ms.openlocfilehash: ba08b12b94847ac130a5f95770ad9cf4c71e0e8c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771993"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 年 2015 年Skype for Business Serverパフォーマンス ツールのポリシーの構成
 
2015 年Skype for Business Serverパフォーマンス ツールのポリシー構成。
  
ストレスとパフォーマンス ツールを実行する前に、Skype for Business Server 2015 で構成できるポリシーと他の領域がいくつかあります。
  
- [アーカイブ ポリシー](configuring-policies.md#ArchivingPolicy)
    
- [会議ポリシー](configuring-policies.md#ConferencingPolicy)
    
- [連絡先ポリシー](configuring-policies.md#ContactsPolicy)
    
- [フェデレーション ポリシー](configuring-policies.md#FederationPolicy)
    
- [通話受付管理ポリシー](configuring-policies.md#CACPolicy)
    
- [音声ルーティング ルール](configuring-policies.md#VoiceRoutingRules)
    
- [会議アテンダント アプリケーション](configuring-policies.md#ConfAttendantApp)
    
- [サーバー コール パーク サービス](configuring-policies.md#ServerCallParkServ)
    
- [緊急通話](configuring-policies.md#EmergencyCalls)
    
- [応答グループ アプリケーションの構成](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>アーカイブ ポリシー
<a name="ArchivingPolicy"> </a>

アーカイブ サーバーがネットワーク トポロジに展開されている場合Skype for Business ServerスクリプトをArchivingPolicy.ps1できます。 さらに支援が必要な場合は、アーカイブコマンドレットと Web 会議コマンドレットを参照してください。
  
## <a name="conferencing-policy"></a>会議ポリシー
<a name="ConferencingPolicy"> </a>

会議の場合は、次のスクリプトMeetingPolicy.ps1があります。 さらに支援が必要な場合は、Web 会議コマンドレットを参照してください。
  
## <a name="contacts-policy"></a>連絡先ポリシー
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1スクリプトは、確認する必要があるサンプルです。 IM and Presence コマンドレットは、さらに参照が必要な場合に役立ちます。
  
## <a name="federation-policy"></a>フェデレーション ポリシー
<a name="FederationPolicy"> </a>

フェデレーションのサンプル スクリプトは、FederationPolicy.ps1。 さらに詳しい情報が必要な場合に確認するコマンドレットは、エッジ サーバー、フェデレーション、および外部アクセスになります。
  
## <a name="call-admission-control-policy"></a>通話受付管理ポリシー
<a name="CACPolicy"> </a>

このポリシーのBandwidthPolicy.ps1参照できます。 通話受付管理コマンドレットには、さらに詳しい情報も含まれています。
  
## <a name="voice-routing-rules"></a>音声ルーティング ルール
<a name="VoiceRoutingRules"> </a>

音声ルーティングのサンプル RoutingRules.ps1が必要です。 これらのルールを構成する場合は、電話コンテキスト (/Location Profile または /SimpleName) と内部/外部エリア コードをメモして、ユーザーの作成時に指定できます。 LyncPerfTool 構成 (特に PSTN-UC および UC-PSTN 用) の間に必要になります。
  
たとえば、RoutingRules.ps1 例の **New-CsDialPlan** コマンドレットの呼び出しの SimpleName パラメーターは、次の図の LocationProfile 値にUserProfileGenerator.exe。
  
![Skype for Businessツール、音声シナリオ タブ、会話の詳細設定を読み込む。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
詳細については、次のコマンドレットをエンタープライズ VoIPできます。
  
## <a name="conference-attendant-application"></a>会議アテンダント アプリケーション
<a name="ConfAttendantApp"> </a>

最初に、スクリプトConferenceAutoAttendantConfiguration.ps1します。 会議AutoAttendant電話番号 (既定では 1121111111) をメモして、以下のように構成生成用の LyncPerfTool 構成ツールに入力します。
  
![電話会議の読み込みレベルと電話番号を示す [音声シナリオ] タブ。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
詳細については、「会議とダイヤルイン会議のコマンドレット」を参照してください。
  
## <a name="server-call-park-service"></a>サーバー コール パーク サービス
<a name="ServerCallParkServ"> </a>

これは、既定では実際には無効になっています。 これをテストする必要があるCallParkConfiguration.ps1サンプル スクリプトを確認できます。 さらに、必要に応じて Call Park Application コマンドレットを確認してください。
  
## <a name="emergency-calls"></a>緊急通話
<a name="EmergencyCalls"> </a>

緊急通話のストレスとパフォーマンス テストを構成するには、次の手順を実行する必要があります。
  
1. 緊急通話の音声ルートを設定します。 この音声ルートの設定RoutingRules.ps1、"Route **E911 to PSTN"** というコメントの下で、このスクリプトを使用して確認できます。
    
    > [!CAUTION]
    > このコマンドの例ではRoutingRules.ps1 911 ではなく 119 という数字パターンがあります。 911 (または実際のローカル緊急電話番号) を使用して、負荷テスト中にローカルの緊急オペレーターへの偶発的な呼び出しを防ぐのは避ける必要があります。 この構成はシミュレーションのみを目的とします。 
  
2. 次の図に示すように、UserProvisioningTool の [位置情報サービス構成] タブの値を入力してアドレスを構成します。 
    
     ![アドレス、サブネット、スイッチ、ポートの数を示すユーザー プロビジョニング ツール。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. UserProvisioningTool にすべてを入力した後、[LIS 構成ファイルの生成] **ボタンをクリック** します。
    
4. これで、ポート、サブネット、スイッチ、ワイヤレス アクセス ポイント (WAP) の CSV ファイルと、ストレスとパフォーマンス ツールの XML ファイルが生成されます。 位置情報サービス (LIS) を構成する際に、入力に CSV ファイルを使用LisConfiguration.ps1できます。 これを行うには、ストレスとパフォーマンス ツールの実行可能ファイル (Locations0.xml) と同じフォルダーにファイルを移動する必要LyncPerfTool.exe。 これにより、場所プロファイル (ダイヤル プラン) のシナリオを実行できます。
    
## <a name="configuring-response-group-application"></a>応答グループ アプリケーションの構成
<a name="ConfigResponseGroupApp"> </a>

サンプル スクリプトは、ResponseGroupConfiguration.ps1。 さらに、構成の詳細を確認する応答グループ アプリケーションコマンドレットも用意されています。 次の図は、構成の詳細の一部を示しています。
  
![テスト用の既存のワークフローを示す応答グループ構成ツール。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

