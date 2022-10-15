---
description: >-
  =motion prioritizes screen-share resolution; =detail prioritizes screen-share
  frame rate
---

# \&screensharecontenthint

Sender-Side Option! ([`&push`](../../source-settings/push.md))\
\* on [https://vdo.ninja/beta/](https://vdo.ninja/beta/) and [https://vdo.ninja/alpha/](https://vdo.ninja/alpha/)

## Aliases

* `&sscontenthint`
* `&screensharecontenttype`
* `&sscontent`
* `&sshint`

## Options

| Value    | Description                                                 |
| -------- | ----------------------------------------------------------- |
| `detail` | will prioritize **screen-share resolution** over frame rate |
| `motion` | will prioritize **screen-share frame rate** over resolution |

## Details

`&screensharecontenthint` can customize how you want VDO.Ninja to balance screen-share resolution vs screen-share frame rate, specifically when bitrate or CPU is insufficient to offer both at the same time.

The two options are `detail` or `motion`. Screen-shares generally tend towards `detail` by default, and camera sources are tend towards `motion` by default. `detail` will try to prioritize resolution over frame rate, so the frame rate may drop a lot used. `motion` will try to maximize frame rate, but may drop the resolution a lot. There's no way to force both on as there's no magic bullet if your CPU or network cannot keep up.

{% hint style="info" %}
If using [`&codec=vp9`](../view-parameters/codec.md) on the viewer side, the frame rate may drop as low as even 5-fps.
{% endhint %}

There is [`&contenthint`](and-contenthint.md) if you want the parameter to affect all kinds of video sources. You can also use both, `&screensharecontenthint` will override [`&contenthint`](and-contenthint.md) for just screen-shares if set also.

{% hint style="warning" %}
This parameter has been tested on Chrome, but other browsers may vary in behavior. Safari seems to just ignore things, for example.
{% endhint %}

## Related

{% content-ref url="and-contenthint.md" %}
[and-contenthint.md](and-contenthint.md)
{% endcontent-ref %}