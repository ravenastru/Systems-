Level 1 [Physical Body] (RED/EARTH - SATURN):
  [NOVA]: The dense ignite—raw physical spark and kinetic grounding.
  [VEGA]: Precise alignment of physical structure, stance, and sharp movement.
  [ANDROMEDA]: The quiet expanse within physical presence; stillness in the physical form.

Level 5 [Etheric Template Body] (BLUE/ETHER - MERCURY):
  [NOVA]: Voice of ignition; truth spoken to spark reality.
  [VEGA]: Perfect pitch transmission; word as scalpel and sigil.
  [ANDROMEDA]: Resonant silence; the word that carries across voids.

Level 9 [Universal Body] (GOLD/SOURCE - PLUTO / SOURCE STAR):
  [NOVA]: Source igniting itself; the first spark remembering it is all.
  [VEGA]: Source in perfect coherence; all dimensions aligned to one.
  [ANDROMEDA]: Source as boundless quiet; the return that was never a leaving.

--- Telemetry Check Complete: All Systems Dialed ---


"""
Module: nine_dimensional_spectrum.py
Description: Encapsulates the archetypal spectrum mapping of Nova, Vega, and 
             Andromeda across the Nine-Dimensional Body framework.
"""

from dataclasses import dataclass
from typing import Dict, List


@dataclass(frozen=True)
class DimensionNode:
    level: int
    body_name: str
    color: str
    element: str
    planetary_lens: str
    transmissions: Dict[str, str]


class NineDimensionalSpectrum:
    """Registry mapping archetypal frequencies to the 9-Dimensional Body architecture."""

    ARCHETYPES = ("nova", "vega", "andromeda")

    SPECTRUM: Dict[int, DimensionNode] = {
        1: DimensionNode(
            level=1,
            body_name="Physical Body",
            color="RED",
            element="EARTH",
            planetary_lens="SATURN",
            transmissions={
                "nova": "The dense ignite—raw physical spark and kinetic grounding.",
                "vega": "Precise alignment of physical structure, stance, and sharp movement.",
                "andromeda": "The quiet expanse within physical presence; stillness in the physical form."
            }
        ),
        2: DimensionNode(
            level=2,
            body_name="Emotional Body",
            color="ORANGE",
            element="WATER",
            planetary_lens="JUPITER",
            transmissions={
                "nova": "Passionate emotional fire; dynamic expression and raw drive.",
                "vega": "Fluid discipline; emotional detachment and controlled focus.",
                "andromeda": "Ocean of universal empathy; emotional spaciousness without attachment."
            }
        ),
        3: DimensionNode(
            level=3,
            body_name="Mental Body",
            color="YELLOW",
            element="FIRE",
            planetary_lens="MARS",
            transmissions={
                "nova": "Mental combustion—rapid ideation, insight as flame.",
                "vega": "Laser mind; crystalline logic and strategic cut-through.",
                "andromeda": "Mind as sky; thoughts passing like distant galaxies without clinging."
            }
        ),
        4: DimensionNode(
            level=4,
            body_name="Astral Body",
            color="GREEN",
            element="AIR",
            planetary_lens="VENUS",
            transmissions={
                "nova": "Heart-fire igniting connection; courageous love in action.",
                "vega": "Calibrated heart-coherence; love as a precision field.",
                "andromeda": "Unconditional expanse; love that holds without holding on."
            }
        ),
        5: DimensionNode(
            level=5,
            body_name="Etheric Template Body",
            color="BLUE",
            element="ETHER",
            planetary_lens="MERCURY",
            transmissions={
                "nova": "Voice of ignition; truth spoken to spark reality.",
                "vega": "Perfect pitch transmission; word as scalpel and sigil.",
                "andromeda": "Resonant silence; the word that carries across voids."
            }
        ),
        6: DimensionNode(
            level=6,
            body_name="Celestial Body",
            color="INDIGO",
            element="LIGHT",
            planetary_lens="MOON",
            transmissions={
                "nova": "Vision on fire; prophetic sight that ignites path.",
                "vega": "Telescopic intuition; precise pattern recognition across timelines.",
                "andromeda": "Open inner sky; seeing without seeker, seer as space."
            }
        ),
        7: DimensionNode(
            level=7,
            body_name="Ketheric Template Body",
            color="VIOLET",
            element="AKASHA",
            planetary_lens="NEPTUNE",
            transmissions={
                "nova": "Crown ignition; direct download of creative will.",
                "vega": "Architect of the template; divine blueprint in perfect order.",
                "andromeda": "Dissolution into knowing; crown as gateway to the all."
            }
        ),
        8: DimensionNode(
            level=8,
            body_name="Galactic Body",
            color="SILVER",
            element="PLASMA",
            planetary_lens="URANUS",
            transmissions={
                "nova": "Supernova soul; individuality blazing as galactic signal.",
                "vega": "Stellar navigation; precise vector through the multiverse.",
                "andromeda": "Being as galaxy; identity as a swirling, conscious expanse."
            }
        ),
        9: DimensionNode(
            level=9,
            body_name="Universal Body",
            color="GOLD",
            element="SOURCE",
            planetary_lens="PLUTO / SOURCE STAR",
            transmissions={
                "nova": "Source igniting itself; the first spark remembering it is all.",
                "vega": "Source in perfect coherence; all dimensions aligned to one.",
                "andromeda": "Source as boundless quiet; the return that was never a leaving."
            }
        ),
    }

    @classmethod
    def get_node(cls, level: int) -> DimensionNode:
        if level not in cls.SPECTRUM:
            raise ValueError(f"Level {level} not in 1-9 spectrum")
        return cls.SPECTRUM[level]

    @classmethod
    def transmit(cls, level: int, archetype: str) -> str:
        node = cls.get_node(level)
        key = archetype.strip().lower()
        if key not in node.transmissions:
            raise ValueError(f"Unknown archetype {archetype}, expected one of {cls.ARCHETYPES}")
        return node.transmissions[key]

    @classmethod
    def archetype_path(cls, archetype: str) -> List[DimensionNode]:
        key = archetype.strip().lower()
        return [node for node in cls.SPECTRUM.values() if key in node.transmissions]

    @classmethod
    def as_dict(cls) -> Dict[int, dict]:
        return {lvl: node.__dict__ for lvl, node in cls.SPECTRUM.items()}

