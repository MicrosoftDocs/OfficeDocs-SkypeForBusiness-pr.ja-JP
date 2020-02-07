---
title: 通話分析を使用して低品質の通話をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: デバイス、ネットワーク、接続に関する通話分析の詳細を使用して、Microsoft Teams および Skype for Business の通話と会議でのユーザーの問題のトラブルシューティングを行います。
ms.openlocfilehash: a9ef3265fa86349ef92c6174c6f561b006af4d1a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836767"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>通話分析を使用して低品質の通話をトラブルシューティングする

通話分析は、Microsoft Teams と Skype for Business の通話や接続の問題のトラブルシューティングに役立ちます。 通話分析には、Office 365 アカウントの各ユーザーの通話と会議のデバイス、ネットワーク、接続に関する詳細情報が表示されます。 通話分析に建物、サイト、テナントの情報が追加されている場合は、通話とセッションごとにも表示されます。 通話分析を通じて提供される情報は、ユーザーが不適切な通話や会議の操作を行った理由を把握するのに役立ちます。 
  
## <a name="call-analytics-permissions"></a>通話分析のアクセス許可

管理者として、通話分析の全機能にアクセスできるようになります。 また、サポートスタッフに Azure Active Directory ロールを割り当てることもできます。 通話分析の限定されたビューが必要なユーザーにチーム通信のサポートスペシャリストの役割を割り当てます。 通話分析の全機能にアクセスする必要があるユーザーに、Teams 通信サポートエンジニアの役割を割り当てます。 どちらの権限レベルでも、Microsoft Teams 管理センターの残りの部分にはアクセスできません。

通信サポートの専門家が、基本的な通話品質の問題を処理します。 会議の問題を調査することはありません。 代わりに、関連情報を収集し、コミュニケーションサポートエンジニアにエスカレートします。 通信サポートエンジニアは、コミュニケーションサポートスペシャリストから非表示になっている詳細な通話ログに情報を表示します。 次の表では、通話分析を使用している場合の通信サポートスペシャリストと通信サポートエンジニアが利用できる情報の概要を示します。

割り当てられたアクセス許可レベルによって、通話分析でどの種類の情報にアクセスできるかが決まります。
  
- **Teams サービス管理者またはチームコミュニケーション管理者**: 通話分析および Microsoft Teams 管理センターのすべての情報にアクセスできます。
    
- **Teams のコミュニケーションサポートスペシャリスト**: 通話分析では、データの一部しか表示されません。 通話のトラブルシューティングを行うことはできますが、チームの通信サポートエンジニアに会議の問題を渡すことになります。 Microsoft Teams 管理センターの残りの部分にはアクセスできません。
    
- **Teams 通信サポートエンジニア**: 通話分析で利用可能なすべてのデータが表示され、通話と会議の両方に関する問題のトラブルシューティングに役立ちます。 Microsoft Teams 管理センターの残りの部分にはアクセスできません。
    
> [!NOTE]
> 通信サポートスペシャリストの役割は、tier 1 のサポートと同等であり、通信サポートエンジニアの役割は tier 2 サポートと同等です。

Teams の管理者ロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。 Teams の通信サポートスペシャリストと Teams の通信サポートエンジニアの役割を詳細に比較するには、「[通話分析を設定](set-up-call-analytics.md#set-call-analytics-permissions)する」をご覧ください。 
  
アクセス許可についてのヘルプが必要な場合は、チームと Skype for Business の管理者にお問い合わせください。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>通話分析を使用して通話品質の問題のトラブルシューティングを行う

1. Teams の通信サポートまたはチーム管理者の資格情報でサインインします。

2. Web ブラウザーで、に*https://admin.teams.microsoft.com*移動します。
    
3. **ダッシュボード**の [**ユーザー検索**] で、通話のトラブルシューティングを行うユーザーの名前または sip アドレスの入力を開始するか、[**ユーザーの表示**] を選択してユーザーのリストを表示します。
    
    ![通話分析の [ユーザーの検索] ボックスのスクリーンショット](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. リストからユーザーを選びます。

5. [**通話履歴**] を選択し、トラブルシューティングする通話または会議を選択します。
    
    ![ユーザーの [通話履歴] ページのスクリーンショット。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. [**詳細設定**] タブを選択し、良好な音質または接続の問題を示す黄色と赤色の項目を探します。
    
    各通話または会議のセッションの詳細では、小さな問題が黄色で表示されます。 (たとえば、次のスクリーンショットでは、平均ジッター、最大ジッター、平均パケット損失率の値が黄色で指定されています)。黄色で表示されているものは、通常の範囲外であり、問題の原因となっている可能性がありますが、この問題の主な原因ではない可能性があります。 赤色の問題は重大な問題であり、このセッションでは通話品質が低下する可能性が高いと考えられます。 
    
    ![ユーザーの通話履歴の [詳細設定] タブのスクリーンショット ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
まれなケースとして、オーディオセッションの品質エクスペリエンスデータが受信されないことがあります。 多くの場合、呼び出しがドロップされ、クライアントが終了して接続されていることが原因です。 この場合、セッションの評価は**利用できません**。
  
Quality of experience (QoE) データを持つオーディオセッションについては、次の表では、セッションが**低**品質と見なされる主な問題について説明します。
  
|**問題**|**分野**|**説明**|
|:-----|:-----|:-----|
|通話の設定  <br/> |Session  <br/> |エラーコード Ms-diag 20-29 は通話の設定に失敗したことを示します。 ユーザーが通話または会議に参加できませんでした。  <br/> |
|オーディオネットワークで分類された低品質通話  <br/> |Session  <br/> |ネットワーク品質の問題 (パケット損失、ジッター、NMOS 劣化、RTT、または隠れた比率など) が発生しました。 不適切な通話の分類に使われる条件の詳細については、 [Microsoft ブログの投稿](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。  <br/> |
|デバイスが機能しない  <br/> |Device  <br/> | デバイスが正常に機能していません。 機能していないデバイスの比率は次のとおりです。 <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   
## <a name="related-topics"></a>関連トピック
[通話分析をセットアップする](set-up-call-analytics.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
