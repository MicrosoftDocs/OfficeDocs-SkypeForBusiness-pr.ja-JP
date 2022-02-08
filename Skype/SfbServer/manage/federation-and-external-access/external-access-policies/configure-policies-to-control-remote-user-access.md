---
title: リモート ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: リモート ユーザーが内部ユーザーと共同作業できるかどうかを制御するために、1 つ以上の外部ユーザー アクセス ポリシー Skype for Business Serverします。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。
ms.openlocfilehash: 6131163d83078f3aa1b9e4c1380a0596cac0837c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384295"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>ユーザーのリモート ユーザー アクセスを制御するポリシーを構成Skype for Business Server

リモート ユーザーが内部ユーザーと共同作業できるかどうかを制御するために、1 つ以上の外部ユーザー アクセス ポリシー Skype for Business Serverします。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。 サイト ポリシーはグローバル ポリシーより優先され、ユーザー ポリシーはサイト ポリシーとグローバル ポリシーより優先されます。 構成できるポリシーの種類の詳細については、「フェデレーションと外部アクセスの管理」を参照[Skype for Business Server。](../managing-federation-and-external-access.md) Skype for Business Serverレベルで適用されるポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

> [!NOTE]  
> 組織のリモート ユーザー アクセスを有効にしていない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、組織のリモート ユーザー アクセスを有効にしているときのみ有効です。 さらに、リモート ユーザー アクセスを制御するユーザー ポリシーを指定した場合、ポリシーは Skype for Business Server に対して有効で、ポリシーを使用するように構成されているユーザーにのみ適用されます。 リモートの場所からユーザーにサインインできるユーザー Skype for Business Server詳細については、「Assign [an external user access policy」を参照してください](assign-an-external-user-access-policy.md)。

リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するには、次の手順を使用します。


> [!NOTE]  
> この手順で説明するのは、リモート ユーザーとの通信を有効にするだけのポリシーを構成する方法ですが、リモート ユーザー アクセスをサポートするため構成する各ポリシーで、フェデレーション ユーザー アクセスやパブリック ユーザー アクセスも構成できます。 フェデレーション ユーザーをサポートするためのポリシーの構成の詳細については、「Configure [policis to control federated](configure-policies-to-control-federated-user-access.md) user access in Skype for Business Server。 パブリック ユーザーをサポートするためのポリシーの構成の詳細については、「[組織の SIP フェデレーション プロバイダー](../sip-providers/manage-sip-federated-providers-for-your-organization.md)を管理する」を参照Skype for Business Server。


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。
    
      - リモート ユーザー アクセスをサポートするグローバル ポリシーを構成するには、グローバル ポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
      - 新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (リモート ユーザーの通信を有効にするユーザー ポリシーの場合は **EnableRemoteUsers** など)。
    
      - 既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。

5.  (オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。

6.  次のどちらかの操作を行います。
    
      - ポリシーのリモート ユーザー アクセスを有効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - ポリシーのリモート ユーザー アクセスを無効にするには、[**リモート ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

7.  [**確定**] をクリックします。

リモート ユーザー アクセスを有効にするには、組織のリモート ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

これがユーザー ポリシーである場合は、リモート接続を許可するユーザーにポリシーを適用する必要もあります。 詳細については、「外部ユーザー アクセス [ポリシーの割り当て」を参照してください](assign-an-external-user-access-policy.md)。
