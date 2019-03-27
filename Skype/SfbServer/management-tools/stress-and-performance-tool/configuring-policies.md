---
title: ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: ポリシーの構成の Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールです。
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881208"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。
 
ポリシーの構成の Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールです。
  
ビジネス サーバー 2015、ストレスおよびパフォーマンス ツールを実行する前に Skype で構成できるようにしていくつかのポリシーがあります。
  
- [アーカイブ ・ ポリシー](configuring-policies.md#ArchivingPolicy)
    
- [会議ポリシー](configuring-policies.md#ConferencingPolicy)
    
- [連絡先のポリシー](configuring-policies.md#ContactsPolicy)
    
- [フェデレーションのポリシー](configuring-policies.md#FederationPolicy)
    
- [受付制御ポリシーします。](configuring-policies.md#CACPolicy)
    
- [音声ルーティングのルール](configuring-policies.md#VoiceRoutingRules)
    
- [会議アテンダント アプリケーション](configuring-policies.md#ConfAttendantApp)
    
- [サーバー コール パーク サービス](configuring-policies.md#ServerCallParkServ)
    
- [緊急電話番号](configuring-policies.md#EmergencyCalls)
    
- [応答グループの構成の適用](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>アーカイブ ・ ポリシー
<a name="ArchivingPolicy"> </a>

ビジネス サーバー トポロジの場合、Skype で展開されたアーカイブ サーバーがあれば、ArchivingPolicy.ps1 スクリプトを検索できます。 サポートが必要なさらに、アーカイブ、Web 会議のコマンドレットをチェック アウトします。
  
## <a name="conferencing-policy"></a>会議ポリシー
<a name="ConferencingPolicy"> </a>

会議で、MeetingPolicy.ps1 スクリプトがあります。 サポートが必要なさらに、Web 会議のコマンドレットをチェック アウトします。
  
## <a name="contacts-policy"></a>連絡先のポリシー
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 スクリプトを確認する必要がありますサンプルとなります。 IM とプレゼンスのコマンドレットは、さらに参照が必要な場合に役立ちます。
  
## <a name="federation-policy"></a>フェデレーションのポリシー
<a name="FederationPolicy"> </a>

フェデレーションで使用するサンプル スクリプトは、FederationPolicy.ps1 です。 コマンドレットを確認して、さらに深めが必要な場合は、エッジ サーバー、フェデレーション、および外部からのアクセスになります。
  
## <a name="call-admission-control-policy"></a>受付制御ポリシーします。
<a name="CACPolicy"> </a>

このポリシーの BandwidthPolicy.ps1 を参照することができます。 呼の受付制御コマンドレットは、さらに同様の情報を必要があります。
  
## <a name="voice-routing-rules"></a>音声ルーティングのルール
<a name="VoiceRoutingRules"> </a>

RoutingRules.ps1 のサンプル スクリプトは、音声ルーティングの必要があります。 これらの規則を構成しているときに注意の内部および外部の市外局番と電話のコンテキストは、/Location のプロファイル (/SimpleName) ユーザーを作成するときに指定することができます。 (具体的には、PSTN UC UC PSTN) の LyncPerfTool の構成時にも必要だぞ。
  
たとえば、次の図の UserProfileGenerator.exe の LocationProfile 値の RoutingRules.ps1 の例では**新規 CsDialPlan**コマンドレットへの呼び出し内のパラメーターに SimpleName を使用してください。
  
![Skype for Business Load Configuration Tool、[Voice Scenarios] タブ、会話の詳細設定](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
詳細については、エンタープライズ VoIP のコマンドレットを確認することができます。
  
## <a name="conference-attendant-application"></a>会議アテンダント アプリケーション
<a name="ConfAttendantApp"> </a>

ConferenceAutoAttendantConfiguration.ps1 スクリプトを最初に確認します。 注意 ConferencingAutoAttendant の電話番号 (既定では、1121111111) を次に示すようなコンフィギュレーションの生成の LyncPerfTool の構成ツールに入力できるようにする必要があります。
  
![電話会議負荷レベルと電話番号を表示している [Voice Scenarios] タブ](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
会議とダイヤルイン会議の詳細がわかりますコマンドレットです。
  
## <a name="server-call-park-service"></a>サーバー コール パーク サービス
<a name="ServerCallParkServ"> </a>

これは実際には既定で無効です。 これをテストする必要がある場合は、CallParkConfiguration.ps1 のサンプル スクリプトを確認できます。 必要に応じて、さらに、コール パーク アプリケーションのコマンドレットをチェックします。
  
## <a name="emergency-calls"></a>緊急電話番号
<a name="EmergencyCalls"> </a>

ストレスおよびパフォーマンスの緊急電話のテストを構成するのには次の手順を実行する必要があります。
  
1. 緊急通報用のボイス ルートを設定します。 RoutingRules.ps1 のスクリプトを使用し、このボイス ルートを設定する方法の例については「 **PSTN にルーティング E911** 」というコメント下を確認できます。
    
    > [!CAUTION]
    > RoutingRules.ps1 のコマンドの例には、911 ではなく、119 の番号を含む番号のパターンがあります。 ロード テスト中に、ローカルの緊急時のオペレーターへの偶発的な呼び出しを防ぐために 911 (または、実際のローカルの緊急電話番号) を使用しないでください。 シミュレーションのためだけには、この構成に注意してください! 
  
2. 次の図に示すように、**場所情報サービスの構成**] タブで、UserProvisioningTool の値を入力してアドレスを構成します。
    
     ![アドレス、サブネット、スイッチ、ポートの数を表示している User Provisioning Tool](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 入力したすべてのもの、UserProvisioningTool、 **LIS 構成ファイルの生成**] ボタンをクリックします。
    
4. 今すぐストレスおよびパフォーマンス ツールの XML ファイルと同様のポート、サブネット、スイッチ、およびワイヤレス アクセス ポイント (Wap)、CSV ファイルが生成されます。 LisConfiguration.ps1 スクリプトを使用して位置情報サービス (LIS) を構成する場合は、入力値の CSV ファイルを使用できます。 これを行うには、ストレスおよびパフォーマンス ツールの実行ファイル (LyncPerfTool.exe) と同じフォルダーに Locations0.xml ファイルを移動する必要があります。 これは、オプションを選択する場所のプロファイル (ダイヤル プラン) のシナリオを実行することができます。
    
## <a name="configuring-response-group-application"></a>応答グループの構成の適用
<a name="ConfigResponseGroupApp"> </a>

サンプル スクリプトは、ResponseGroupConfiguration.ps1 です。 構成の詳細を確認するのには応答グループ アプリケーションのコマンドレットが用意されています。 次の図は、いくつかの構成の詳細に表示されます。
  
![既存のテスト用ワークフローを表示している Response Group Configuration Tool](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

