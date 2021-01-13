---
title: リモート ユーザー アクセスを制御するポリシーの構成
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1 つ以上の外部ユーザー アクセス ポリシーを構成して、リモート ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御します。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817302"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Skype for Business Server でリモート ユーザー アクセスを制御するポリシーを構成する

1 つ以上の外部ユーザー アクセス ポリシーを構成して、リモート ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御します。 リモート ユーザー アクセスを管理するため、グローバル、サイト、およびユーザー レベルでポリシーを構成できます。 サイト ポリシーはグローバル ポリシーより優先され、ユーザー ポリシーはサイト ポリシーとグローバル ポリシーより優先されます。 構成できるポリシーの種類の詳細については、「Skype for Business Server へのフェデレーションと外部アクセスの管理」 [を参照してください](../managing-federation-and-external-access.md)。 あるポリシー レベルで適用される Skype for Business Server ポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

> [!NOTE]  
> 組織のリモート ユーザー アクセスを有効にしていない場合でも、リモート ユーザー アクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、組織のリモート ユーザー アクセスを有効にしているときのみ有効です。 さらに、リモート ユーザー アクセスを制御するユーザー ポリシーを指定した場合、このポリシーは、Skype for Business Server が有効で、ポリシーを使用するように構成されているユーザーにのみ適用されます。 リモートの場所から Skype for Business Server にサインインできるユーザーの指定の詳細については、「外部ユーザー アクセス ポリシーを割り当てる [」を参照してください](assign-an-external-user-access-policy.md)。

リモート ユーザー アクセスの制御に使用する各外部アクセス ポリシーを構成するには、次の手順を使用します。


> [!NOTE]  
> この手順で説明するのは、リモート ユーザーとの通信を有効にするだけのポリシーを構成する方法ですが、リモート ユーザー アクセスをサポートするため構成する各ポリシーで、フェデレーション ユーザー アクセスやパブリック ユーザー アクセスも構成できます。 フェデレーション ユーザーをサポートするポリシーの構成の詳細については [、「Configure policies to control federated user access in Skype for Business Server 」を参照してください](configure-policies-to-control-federated-user-access.md)。 パブリック ユーザーをサポートするポリシーの構成の詳細については、「Skype for Business Server で組織の SIP フェデレーション プロバイダーを管理する [」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>リモート ユーザー アクセスをサポートする外部アクセス ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 

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
