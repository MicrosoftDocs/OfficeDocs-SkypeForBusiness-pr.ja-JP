---
title: Microsoft Teams のクラウド ビデオ相互運用性の設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: この記事では、組織内のユーザーに対してクラウドビデオの相互運用機能を計画してセットアップする方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b171b3fb5e73561ea5aea54e6e4f25bfabe6b0dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198863"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用性の設定

[クラウドビデオ相互運用パートナーを選択](cloud-video-interop.md)した後は、展開を計画し、プロビジョニングの詳細とパートナーのテナントキーを設定して、組織内のビデオ相互運用機能アプリへの同意を得る必要があります。 次の図は、プロセスの概要を示しています。 

![組織での CVI の展開](media/deploying-cvi.png)

## <a name="plan"></a>プラン

組織で使用するパートナーまたはパートナーを特定する方法については、「 [Microsoft Teams のクラウドビデオ相互運用機能](cloud-video-interop.md)」を参照してください。 

ユーザーに基づく、同時、またはサイト全体の有効化を計画するには、次の操作を行います。 

- 使用する展開モデル/ホストモデルを選ぶ
- 組織に最適なライセンスプランを選択します。 
- Vm の容量を計画するには、ビデオインフラストラクチャをホストしている必要があります。

## <a name="configure"></a>構成 

クラウドビデオ相互運用機能を構成するには、次の手順を実行します。 

1. 選択したパートナー/パートナーから構成情報を取得します (テナントキー、appIds...)。 組織では、1つ以上のビデオ相互運用パートナーを使用できます。 

2. ネットワークが正しく構成されていることを確認します。 境界ネットワークトラバーサルをサポートするために、標準ベースのビデオファイアウォールを構成します。 次に例を示します。 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 統合された会議室を exchange と OTD で構成します。 ほとんどの場合、追加の中継は環境で設定して構成する必要があります。


## <a name="provision"></a>規定
 
テナントキーは、パートナーサービスへのダイヤルアウトになります。 次の例では、813878896@t.plcm.vc はテナントキーです。 

![テナントキーの例](media/tenant-key-example.png) 

テナントキーをプロビジョニングするには、次のコマンドレットを実行する必要があります。また、選択したユーザーまたは組織全体で、ビデオ相互運用機能による会議を作成することもできます。

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft は、クラウドビデオ相互運用に使用するパートナーを指定することができる、サポートされている各パートナーの事前構築ポリシーを提供しています。

    このコマンドレットでは、組織で使用できる事前構築済みのポリシーを識別できます。 このポリシーは、Grant-CsTeamsVideoInteropServicePolicy コマンドレットを利用する1人以上のユーザーに割り当てることができます。
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するために事前構築されたポリシーを割り当てることができます。または、特定のユーザーにポリシーを割り当てることもできます。
 
- **[新規-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 組織で使用する、サポートされている CVI パートナーに関する情報を指定するには、CsVideoInteropServiceProvider を使用します。
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** CsVideoInteropServiceProvider を使用して、組織が使用するサポートされている CVI パートナーに関する情報を更新します。
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** 組織内で使用するように構成されているすべてのプロバイダーを取得します。
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** 組織で使用されなくなったプロバイダーに関するすべてのプロバイダー情報を削除するには、CsVideoInteropServiceProvider を使用します。  
 
## <a name="consent"></a>同意

パートナーサービス経由で組織の会議に参加するには、ビデオ会議デバイス (VTCs) に対するアクセス許可の同意を提供する必要があります。 この同意リンクは、パートナーによって提供されることもあります。  
 
これらの手順を完了すると、上記の Grant コマンドレット、またはテナントが有効になっている場合、組織内のすべてのユーザーに対して個別に許可されているユーザーには、スケジュールされているすべてのチーム会議の VTC 座標が含まれます。 任意の VTC は、これらの調整を通じてこれらの会議に参加できます。


|名前|アプリケーションアクセス許可の短い説明| 説明|
|--|--|---|
|JoinGroupCall を呼び出します。|グループ通話と会議をアプリとして参加する (プレビュー)|サインインしているユーザーがいなくても、アプリがグループ通話や組織内のスケジュールされた会議に参加することを許可します。  アプリは、テナントの会議にディレクトリユーザーの権限と共に参加します。|
|JoinGroupCallasGuest を呼び出します。|ゲストユーザーとしてグループ通話と会議に参加する (プレビュー)|サインインしているユーザーがいなくても、アプリがグループ通話と組織内のスケジュールされた会議に匿名で参加することを許可します。  アプリは、テナントの会議にゲストとして参加します。|
|アクセスメディア。すべて|アプリとしての通話でのメディアストリームへのアクセス (プレビュー)|サインインしているユーザーがいなくても、アプリが通話中のメディアストリームに直接アクセスすることを許可します。|
|OnlineMeetings|オンライン会議の詳細を読む (プレビュー)|サインインしているユーザーがいなくても、組織内のオンライン会議の詳細をアプリで読むことができます。|

## <a name="schedule"></a>基点

次に、ビデオ相互運用機能の調整を使って Teams 会議をスケジュールします。 有効なユーザーは、次の方法で teams 会議をスケジュールできます。
- [Outlook 用 Teams 会議アドイン](teams-add-in-for-outlook.md)
- Teams クライアントのデスクトップとモバイル


## <a name="join"></a>Join

次のような方法で、チーム会議に VTC デバイスと参加することができます。
 
- IVR (インタラクティブな音声応答)
    - Tenantkey @ domain を使って、パートナーの IVR にダイヤルインすることができます。 
    - パートナー IVR に参加すると、VTC conferenceId を入力するように求められます。これにより、Teams の会議に接続されます。
- ダイレクトダイヤル
    - このダイレクトダイヤル機能を使用すると、パートナーの IVR と直接やり取りすることなく、チーム会議に直接ダイヤルできます。VTC ConferenceId @ domain
- ワンタッチダイヤル
    - 統合されたチームルームがある場合は、パートナーが提供するワンタッチダイヤル機能を使用できます (ダイヤル文字列を入力する必要はありません)。

最後に、音声、ビデオ、およびコンテンツ共有を使用して、会議の Teams ユーザーと協力します。 