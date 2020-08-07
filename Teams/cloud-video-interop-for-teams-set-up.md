---
title: Microsoft Teams のクラウド ビデオ相互運用機能の設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: この記事では、組織内のユーザーについてクラウド ビデオ相互運用を計画して設定する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582634"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用機能の設定

[クラウド ビデオ相互運用パートナーを選択](cloud-video-interop.md)した後は、展開を計画し、プロビジョニングの詳細とパートナーのテナント キーを使用して設定を行い、組織のビデオ相互運用アプリに同意する必要があります。 この手順を次の図に示します。 

![組織で CVI を展開する](media/deploying-cvi.png)

## <a name="plan"></a>計画

組織で使用するパートナーを特定する方法については、「[Microsoft Teams のクラウド ビデオ相互運用](cloud-video-interop.md)」を参照してください。 

ユーザー ベース、同時、サイト全体での有効化を計画するには 

- 使用する展開モデルやホスト モデルを選ぶ
- 組織に最適なライセンス プランを選択する 
- ビデオ インフラストラクチャをホストしている VM の容量を計画する

## <a name="configure"></a>構成 

クラウド ビデオ相互運用を構成するには、次の手順を実行します。 

1. 選択したパートナーから構成情報 (テナント キー、アプリ ID など) を入手します。 組織では、1 つまたは複数のビデオ相互運用パートナーを使用できます 

2. ネットワークが正しく構成されていることを確認します。 境界ネットワーク トラバーサルをサポートするために、標準ベースのビデオ ファイアウォールを構成します。 次に例を示します。 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 統合された会議室を Exchange と OTD を使用して構成します。 ほとんどの場合、追加の中継は、環境でセットアップして構成する必要があります。


## <a name="provision"></a>プロビジョニング
 
テナント キーは、パートナー サービスへのダイヤル アウトになります。 次の例では、813878896@t.plcm.vc がテナント キーです。 

![テナント キーの例](media/tenant-key-example.png) 

テナント キーをプロビジョニングするには、次のコマンドレットを実行する必要があります。また、選択したユーザーまたは組織全体がビデオ相互運用座標を使用して会議を作成できるようになります。

 
- **[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft では、サポート対象の各パートナーに対して、クラウド ビデオ相互運用性に使用するパートナーを指定できる事前構築ポリシーを提供しています。

    このコマンドレットは、組織内で使用できる事前構築ポリシーを指定できます。 Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用して、このポリシーを 1 人または複数のユーザーに割り当てることができます。
 
- **[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するために事前構築されたポリシーを割り当てたり、特定のユーザーにポリシーを割り当てたりすることができます。
 
- **[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** New-CsVideoInteropServiceProvider を使用して、組織が使用するサポート対象の CVI パートナーに関する情報を指定します。
 
- **[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Set-CsVideoInteropServiceProvider を使用して、組織が使用するサポート対象の CVI パートナーに関する情報を更新します。
 
- **[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** 組織内で使用するために構成されているすべてのプロバイダーを取得します。
 
- **[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Remove-CsVideoInteropServiceProvider を使用して、組織で使用しなくなったプロバイダーに関するすべてのプロバイダー情報を削除します。  
 
## <a name="consent"></a>同意

パートナー サービスを介して組織の会議に参加するには、ビデオ会議デバイス (VTC) に対するアクセス許可の同意を付与する必要があります。 また、この同意リンクはパートナーによって提供されます。  
 
これらの手順が完了すると、上記の Grant コマンドレットを使用して個別に有効にされたユーザー、またはテナントが有効な場合は組織内のすべてのユーザーが、スケジュールされているすべての Teams 会議において VTC 座標を持つようになります。 すべての VTC は、これらの座標を使用してこれらの会議に参加できます。


|名前|アプリケーションのアクセス許可の簡潔な説明| 説明|
|--|--|---|
|Calls.JoinGroupCall.All|グループ通話と会議にアプリとして参加する (プレビュー)|アプリで、サインインしているユーザーがいなくても、組織のグループ通話やスケジュールされた会議に参加することができるようにします。  このアプリでは、ディレクトリ ユーザーの特権を使用してテナントの会議に参加します。|
|Calls.JoinGroupCallasGuest.All|グループ通話と会議にゲスト ユーザーとして参加する (プレビュー)|アプリで、サインインしているユーザーがいなくても、組織のグループ通話とスケジュールされた会議に匿名で参加することができるようにします。  このアプリは、テナントの会議にゲストとして参加します。|
|Calls.AccessMedia.All|通話内のメディア ストリームにアプリとしてアクセスする (プレビュー)|アプリで、サインインしているユーザーがいなくても、通話内のメディア ストリームに直接アクセスすることができるようにします。|
|OnlineMeetings.Read.All|オンライン会議の詳細を読み取る (プレビュー)|アプリで、サインインしているユーザーがいなくても、組織内のオンライン会議の詳細を読み取ることができるようにします。|

## <a name="schedule"></a>スケジュール

次に、ビデオ相互運用座標を使用して Teams 会議をスケジュールします。 有効なユーザーは、次のようにして Teams 会議をスケジュールできます。
- [Outlook 用 Teams 会議アドイン](teams-add-in-for-outlook.md)
- チーム クライアントのデスクトップとモバイル


## <a name="join"></a>参加

次の方法で、Teams 会議を VTC デバイスと結合できます。
 
- IVR (対話型音声応答)
    - tenantkey@domain を使用して、パートナーの IVR にダイヤルインできます。 
    - パートナー IVR に入ると、VTC conferenceId を入力するように求められます。これにより、Teams 会議に接続されます。
- 直接ダイヤル
    - TenantKey の全文字列を使用して、直接ダイヤル機能を使用すると、パートナーの IVR に対する操作なしに、Teams 会議に直接ダイヤルインできます。VTC ConferenceId@domain。
- ワンタッチ ダイヤル
    - Teams ミーティングが統合されている場合は、パートナーが提供するワンタッチ ダイヤル機能を使用できます (ダイヤルの文字列を入力する必要はありません)。

最後に、音声、ビデオ、コンテンツ共有を使用して、Teams ユーザーと打ち合わせを行います。 
