# Awesome Asterisk [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Open source tools, libraries and resources for building on [Asterisk](https://www.asterisk.org), the telephony toolkit behind a large share of the world's PBXs, contact centres and voice platforms.

Asterisk gives you call control and a media path. Almost everything else, the interface, the dialler, the monitoring, the security, comes from the ecosystem around it. This list covers that ecosystem, plus the SIP and media components Asterisk is usually deployed alongside.

Every entry was checked against its own repository before being listed. Projects that stopped being maintained are removed rather than left in place, because a directory that lists dead software costs people more time than it saves.

## Contents

- [Official](#official)
- [Distributions and web interfaces](#distributions-and-web-interfaces)
- [ARI, AMI and AGI libraries](#ari-ami-and-agi-libraries)
- [Streaming call audio](#streaming-call-audio)
- [Voice AI](#voice-ai)
- [SIP proxies and session border control](#sip-proxies-and-session-border-control)
- [Media and RTP](#media-and-rtp)
- [Testing and troubleshooting](#testing-and-troubleshooting)
- [Security](#security)
- [Contact centre and dialling](#contact-centre-and-dialling)
- [Endpoints](#endpoints)
- [Learning](#learning)
- [Disclosure](#disclosure)

## Official

- [Asterisk](https://github.com/asterisk/asterisk) - The telephony toolkit itself. Channel drivers, dialplan, and the ARI and AMI interfaces everything else is built on.
- [Asterisk documentation](https://docs.asterisk.org) - Official documentation, versioned and generated from its own repository.
- [Asterisk community](https://community.asterisk.org) - Where the maintainers actually answer questions.
- [Asterisk Test Suite](https://github.com/asterisk/testsuite) - The functional test framework the project runs against itself.

## Distributions and web interfaces

- [FreePBX](https://github.com/FreePBX/framework) - The long-running web administration layer over Asterisk, and the usual first stop if you want a working PBX today.
- [Issabel](https://github.com/IssabelFoundation/issabelPBX) - Community distribution carrying on the all-in-one unified communications shape.
- [Wazo Platform](https://github.com/wazo-platform/wazo-platform) - Asterisk based platform built API first, for people constructing a service rather than administering a box.

## ARI, AMI and AGI libraries

- [node-ari-client](https://github.com/asterisk/node-ari-client) - Official Node.js client for the Asterisk REST Interface.
- [ari](https://github.com/CyCoreSystems/ari) - Idiomatic Go client for ARI, with a NATS transport option for distributed setups.
- [asterisk-java](https://github.com/asterisk-java/asterisk-java) - Mature Java library covering AMI, AGI and the FastAGI server.
- [Panoramisk](https://github.com/gawel/panoramisk) - Python asyncio library for AMI and AGI.
- [PAMI](https://github.com/marcelog/PAMI) - PHP client for the Asterisk Manager Interface, event driven.
- [agi](https://github.com/zaf/agi) - Small Go package for writing AGI and FastAGI handlers.
- [asterisk-ami-node](https://github.com/ictinnovations/asterisk-ami-node) - Dependency-free typed AMI client for Node.js.

## Streaming call audio

Getting live call audio into your own process, which is the starting point for transcription, recording and voice AI.

- [asterisk-external-media](https://github.com/asterisk/asterisk-external-media) - Official examples of the External Media channel, the ARI route for streaming audio out over RTP.
- [audiosocket](https://github.com/CyCoreSystems/audiosocket) - Go implementation of the AudioSocket protocol, which bridges a call into a plain TCP socket.
- [asterisk-audiosocket](https://github.com/ictinnovations/asterisk-audiosocket) - Dependency-free TypeScript implementation of the same protocol, with paced playback helpers.

## Voice AI

- [Whisper](https://github.com/openai/whisper) - Speech recognition models that changed what is affordable in this space.
- [whisper.cpp](https://github.com/ggml-org/whisper.cpp) - The port that made Whisper practical on ordinary CPUs, which is what most people run next to a PBX.
- [Vosk](https://alphacephei.com/vosk/) - Lightweight offline speech recognition with streaming support and small models, well suited to telephony audio.
- [Piper](https://github.com/OHF-Voice/piper1-gpl) - Fast local neural text to speech, light enough to run per channel.
- [asterisk-ai-voice-agent](https://github.com/ictinnovations/asterisk-ai-voice-agent) - Self-hosted voice agent for Asterisk over AudioSocket or chan_websocket, with barge-in handling.
- [tvbench](https://github.com/ictinnovations/telephony-voice-agent-benchmark) - Measures what a caller actually hears from a voice agent: frame pacing, gaps and barge-in.

## SIP proxies and session border control

Signalling at carrier volume is a different job from running a PBX, and mixing the two is an expensive architecture mistake.

- [Kamailio](https://github.com/kamailio/kamailio) - SIP proxy, registrar and router built for very high signalling throughput.
- [OpenSIPS](https://github.com/OpenSIPS/opensips) - The other branch of the same lineage, strong on session border control and provider-side routing.

## Media and RTP

- [rtpengine](https://github.com/sipwise/rtpengine) - Kernel assisted RTP proxy and media relay, handling NAT traversal, recording and transcoding at volume.
- [coturn](https://github.com/coturn/coturn) - The STUN and TURN server nearly every WebRTC deployment ends up running.
- [SpanDSP](https://github.com/freeswitch/spandsp) - DSP library covering fax modulation, tone handling and echo cancellation.

## Testing and troubleshooting

- [SIPp](https://github.com/SIPp/sipp) - Traffic generator and test tool for SIP. Still the standard way to load test a signalling path.
- [sngrep](https://github.com/irontec/sngrep) - Terminal SIP capture with call flow diagrams. The fastest way to see what is happening on a box you are logged into.
- [HOMER](https://github.com/sipcapture/homer) - SIP capture and correlation across a whole estate, so you can reconstruct one call across every hop.
- [heplify](https://github.com/sipcapture/heplify) - Lightweight HEP capture agent that feeds HOMER.
- [asterisklint](https://github.com/ossobv/asterisklint) - Static analysis for Asterisk configuration and dialplan.

## Security

- [SIPVicious](https://github.com/EnableSecurity/sipvicious) - The security tool suite for auditing SIP systems. Run it against your own before someone else does.

## Contact centre and dialling

- [VICIdial](https://www.vicidial.org) - Web based inbound and outbound contact centre suite over Asterisk, with predictive dialling. Widely deployed and commercially supported.
- [GOautodial](https://github.com/goautodial/v4.0) - Contact centre distribution in the same territory, with its own interface and API.

## Endpoints

- [Linphone](https://github.com/BelledonneCommunications/linphone-desktop) - SIP client across desktop and mobile with encrypted voice and video, and a library you can embed.
- [baresip](https://github.com/baresip/baresip) - Modular SIP user agent, useful both as a scriptable endpoint and as a base for custom clients.

## Learning

- [PhreakScript](https://github.com/InterLinked1/phreakscript) - Build and feature script that also serves as a deep, opinionated tour of lesser known Asterisk internals.
- [Asterisk: The Definitive Guide](https://www.asteriskdocs.org) - The community book, freely readable online.

## Disclosure

This list is maintained by [ICT Innovations](https://www.ictinnovations.com), who also build some of the software on it. Entries we maintain are `asterisk-ami-node`, `asterisk-audiosocket`, `asterisk-ai-voice-agent` and `tvbench`. They are held to the same bar as everything else and can be challenged in an issue like any other entry.

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first, and please open one pull request per entry.
