<h1 align='center'>Una Marsh</h1>

<p align='center'>wetland ecology postgraduate · Bristol · <code>@eumarsh</code></p>

<table width='100%'>
  <tr>
    <td width='60%' valign='top'>
      <h3>This week's work</h3>
      <p>I am comparing water-level records from dip wells and pressure loggers in reed-fen ditches, trying to tell real wet-and-dry cycles apart from calibration drift. The sites are damp, windy, and full of slightly inconsistent timestamps.</p>
      <p>At University of the West of England, Bristol, my research sits between field ecology and practical data work. I care about tools that are small enough to understand after a long day outside and strict enough to make the next analysis trustworthy.</p>
      <h3>Two questions I keep returning to</h3>
      <ul>
        <li><strong>How long was the ground actually wet?</strong> A logger can report a neat hourly series, but missing visits and shifted sampling intervals can hide the short dry periods that change plant roots and invertebrate habitat.</li>
        <li><strong>What can a photograph honestly quantify?</strong> Quadrat photos are useful for cover estimates and labels, but lighting, angle, and late-season vegetation can make an automatic classification sound more certain than it is.</li>
      </ul>
    </td>
    <td width='40%' valign='top'>
      <h3>Usually carrying</h3>
      <p><code>dip tape</code> · <code>pressure logger</code> · notebook · rain trousers · spare bags for muddy boots</p>
      <h3>How I like to collaborate</h3>
      <ul>
        <li>Paper notes first, typed checks later.</li>
        <li>Issues should include a tiny sample of the data that failed.</li>
        <li>I prefer obvious functions over clever abstractions.</li>
      </ul>
      <h3>Offline interests</h3>
      <p>Slow walks on the Levels, ditch plants, weather radar, and weekend notes about how water changes the shape of a place.</p>
    </td>
  </tr>
</table>

---

### From a muddy logger to a readable table

Most of my tools begin because one spreadsheet has used three different date formats in the same column.

<pre>
read raw logger file
        |
        v
parse timestamp + measurement
        |
        +--> flag duplicate or impossible times
        |
        v
correct for local atmospheric pressure
        |
        v
convert clock time to consistent UTC intervals
        |
        v
write checked CSV + plain-text field note
</pre>

The tricky step is often the timestamp conversion. Field devices may be set to local time, laptops may quietly reinterpret the file, and daylight-saving changes can create gaps or duplicates. I try to preserve the original reading, add a separate corrected timestamp, and never overwrite the only copy of a raw record.

---

### Learning notes and uncertainties

- A graph that looks smooth is not necessarily reliable. Smooth lines can come from interpolation, and interpolation can hide the fact that a logger was not recording.
- Barometric correction is less intimidating than it first appears, but small offset errors matter when ditch levels change by only a few centimetres.
- Naming files by site, date, and device helps, but only if the convention is short enough to use while cold and wet.
- Ecological labels are often provisional. <code>bare ground</code>, <code>open water</code>, and <code>litter</code> can overlap in one photograph, and forcing a single label can remove useful ambiguity.
- I have learned to write down the thing I assumed was obvious: which end of the dip tube was up, whether the battery was changed, and whether a cow had recently stood on the boardwalk.

---

### Small prototypes

#### <code>dipwell-check</code>

A command-line script for reading pressure-logger exports, flagging duplicate timestamps, and reporting impossible jumps before analysis. The tradeoff is that it currently supports only the two device formats my team actually uses. Adding every possible export format now would make it broader but less tested. The next step is a small validation report that can be attached to a field season folder without claiming the data are final.

#### <code>quadrat-labels</code>

A notebook for renaming and grouping quadrat photographs from field labels, then producing a cautious review sheet rather than an automatic species label. I am experimenting with simple image hashes to detect accidental duplicates, but I am keeping human review in the middle because reflections and dead reeds confuse quick visual comparisons.

Neither project is meant to become a large framework. They are attempts to remove repetitive spreadsheet work while keeping ecological judgement visible.

---

### My route into wetlands

I did not arrive through a polished plan. During my undergraduate dissertation, I spent weeks sorting invertebrates from ditch samples and became preoccupied with how much life depended on water levels that were easy to overlook. After volunteering on wetland survey days, I learned that I enjoyed the unglamorous part: checking logs, revisiting sites, and matching what the data said to what the habitat looked like.

That habit carried into postgraduate work. I like the meeting point of careful field craft and reproducible code, where a ten-centimetre change can alter which plants persist and a correctly parsed timestamp can change the whole conclusion.

<details>
<summary>Supplementary weekend notes from the Somerset Levels</summary>

On weekends I write short field essays about rhynes, flood marks, seasonal light, and the clues that show whether a wetland has been recently saturated. These are not research outputs; they are a way to practise noticing. I often return to the same spot after rain and compare what changed with what I expected to change.

</details>
